# Examples

### Update User Status&#x20;

Let's create a new slash command that takes two parameters. The first is the status value (online, away, busy, etc.), while the second is discretionary and contains the status text. We will refer to the status slash command as st so we can execute code such as this:

```
/st away Doing code :)
```

The new class will be named `StatusUpdateCmd` and will be placed in the same subdirectory as `commands`. Now, we add the relevant code for the status update to the executor. We require a single argument with the status value to be modified; otherwise, we use our `notifyMessage` to inform the user that the argument is missing. Thus we are:

* Fetching the status from the first argument.
* Fetching the status message from the second argument onwards joining the terms by a white space. If they are not passed we just use as the status message an empty string.
* We use the ‘modify’ User updater to update the status accordingly.
* Finally, we notify the user about the status update.

```typescript
export class StatusUpdateCmd implements ISlashCommand {
   command: string;
   i18nParamsExample: string = 'status_update_command_params_example';
   i18nDescription: string = 'status_update_command_description';
   providesPreview: boolean = false;
   async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp, persis: IPersistence): Promise<void> {
       const user = context.getSender();
       const params = context.getArguments();
       const room: IRoom = context.getRoom();
       if (!params || params.length == 0) {
           return notifyMessage(room, read, user, "At least one status argument is mandatory. A second argument can be passed as status text.");
       }
       let status = params[0];
       let statusText = params.length > 1 ? params.slice(1).join(' ') : '';
       modify.getUpdater().getUserUpdater().updateStatus(user, statusText, status);
       notifyMessage(room, read, user, "Status updated to " + status + " (" + statusText + ").");
   }
}

```

\
**Note:** If applicable, change the localization file and update the main class's extendConfiguration to register the new slash command. All that remains is deployment and testing.

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/XJs5iHML3qvpXmlMm7arHQrLHxLSH1utsMnZozAA0-fsoYAUdFvOLj80yA7T7HLLEQKn7ZPj4uICWblde2JINJ3v8JQ62ln4lsqhzEsQZce8yvI3Gnmwkzh6pPHiUGyhR3-tl_q0lZPChZztDArs5mM" alt=""><figcaption></figcaption></figure>

</div>

And if we execute '`/st`' with no input, we will also receive the notification:

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/p5BjJCHrjp8fP8EfiambuJsd-gnMAHVJpaSbTRKtFNLFhk9RpCq7UVN-49XKU0LbYT9Yl00crxFdAYLvqmxYwSndJrEgyJC8phsIO4yib7rgtphqeGL8Bnurg7IoMADzncAsyTLz7SuyRTNRifz57jI" alt=""><figcaption></figcaption></figure>

</div>

### Extending Messages

This section explains how to modify messages to include custom fields and attachments. We will construct an application that is invoked via a slash command, sends a message, and is extended to include an image and a custom field.&#x20;

#### Attachments&#x20;

Attachments Rocket.Chat supports numerous forms of attachments that can be attached to messages (and applicable customizations to these attachments). For instance, you can attach images, documents, videos, and audio files to messages; the first step in doing so is to create your own attachment class.

In this approach, we will implement the `ImageAttachment` class in the project's root as follows:

```typescript
import { IMessageAttachment } from '@rocket.chat/apps-engine/definition/messages';

export class ImageAttachment implements IMessageAttachment{
    imageUrl?: string; // [1]

    constructor(imgUrl: string){
        this.imageUrl = imgUrl;
    }

}
```

Here, we \[1] use a class' attribute with the same identifier and type as in the `IMessageAttachment` interface, which is required for your linked media to be visible to the user (since only the variables in your attachment class that are defined in the `IMessageAttachment` interface will be used to retrieve the attachment's media).

You can also construct your own classes for video or audio attachments, or you can group them all into a single class that can accommodate all of these possibilities. Just be sure to use the same attributes described in the `IMessageAttachment.d.ts` file.

**Note:** The audio and video formats supported in Rocket.Chat message attachments are identical to HTML audio and video elements.

#### Custom Fields

Custom fields are structures linked to messages in which each field is organized as if it were an entry in a dictionary. In other words, each field must contain a key and corresponding value. These elements are retained in the server's database alongside their corresponding messages so they can be retrieved later.

#### Create new auxiliary methods&#x20;

It is beneficial to define a few auxiliary methods within our slash command class so that our code remains concise and straightforward.

**Method: sendMessage**

First, we must modify the previously provided `sendMessage` method so that the message's ID is returned after it has been sent. The method must now return a `Promise<string>` as opposed to a `Promise<void>`.

The ensuing `sendMessage` method is detailed below:

```typescript
private async sendMessage(context: SlashCommandContext, modify: IModify, message: string): Promise<string> {
    const messageStructure = modify.getCreator().startMessage();
    const sender = context.getSender();
    const room = context.getRoom();

    messageStructure
    .setSender(sender)
    .setRoom(room)
    .setText(message);

    return (await modify.getCreator().finish(messageStructure)); // [1]
}

```

The only change that must be made (in comparison to the `sendMessage` described in previous pages) is \[1] to return the result of the `finish` method, which is the ID of the message that has just been sent.

**Method: getMessageExtender**

After modifying the `sendMessage` method and obtaining the message's ID, we can now acquire the `messageExtender` object, which enables the addition of custom fields and attachments.

In order to obtain the `messageExtender` object, the following asynchronous method can be used:

```typescript
private async getMessageExtender(context: SlashCommandContext, modify: IModify, messageId: string): Promise<IMessageExtender>{
    const sender = context.getSender();
    return modify.getExtender().extendMessage(messageId, sender); // [1]
}
```

Here, \[1]  we use the message's ID returned by the `sendMessage` method in order to obtain the `messageExtender` object using the `modifyExtender` object.

After developing the methods, you only need to invoke them with a slash command. You must adhere to the procedures outlined in the preceding section:&#x20;

1. Register the slash command
2. Create the slash command
3. Deploy to the server
4. Test the slash command&#x20;

### Step 1: Register the slash command

We have to register it in the app's main class, in the project's root.

```typescript
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { ExtendMessageCommand } from './slashcommands/ExtendSlashcommand'; // [1]

export class RocketChatTester extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async extendConfiguration(configuration: IConfigurationExtend) {
        configuration.slashCommands.provideSlashCommand(new ExtendMessageCommand()); // [2]
    }
}
```

Here we \[1] import our new slash command class and then \[2] register it in the app's configuration.&#x20;

### Step 2: Create the slash command&#x20;

```typescript
import { IHttp, IModify, IPersistence, IRead, IMessageExtender } from '@rocket.chat/apps-engine/definition/accessors';
import { ISlashCommand, SlashCommandContext } from '@rocket.chat/apps-engine/definition/slashcommands';
import { ImageAttachment } from '../ImageAttachment';

export class ExtendMessageCommand implements ISlashCommand{
    public command = 'extend-message';
    public i18nParamsExample = '';
    public i18nDescription = '';
    public providesPreview = false;

    public async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp, persis: IPersistence): Promise<void> {
        const messageId = await this.sendMessage(context, modify, 'Sending a message!'); // [1]
        const messageExtender = await this.getMessageExtender(context, modify, messageId); // [2]
        const value = 1;
        const img = new ImageAttachment('https://open.rocket.chat/images/logo/logo.svg'); // [3]

        messageExtender.addCustomField('key', value); // [4]
        messageExtender.addAttachment(img); // [5]

        await modify.getExtender().finish(messageExtender); // [6]
    }

    private async sendMessage(context: SlashCommandContext, modify: IModify, message: string): Promise<string> {
        const messageStructure = modify.getCreator().startMessage();
        const sender = context.getSender();
        const room = context.getRoom();

        messageStructure
        .setSender(sender)
        .setRoom(room)
        .setText(message);

        return (await modify.getCreator().finish(messageStructure));
    }
    private async getMessageExtender(context: SlashCommandContext, modify: IModify, messageId: string): Promise<IMessageExtender>{
        const sender = context.getSender();
        return modify.getExtender().extendMessage(messageId, sender);
    }
}

```

The main actions performed by the code above are:

* \[1] Sends a message and stores the sent message's ID in the messageId variable;
* \[2] Uses the sent message's ID. The `messageExtender` object is returned by the `getMessageExtender` method and stored in the `messageExtender` variable;
* \[3] Creates the attachment object as an instance of the `ImageAttachment` class. Here, the attachment is an image;
* \[4] Adds a custom field with the key '`key`' linked to the value 1 using the `addCustomField` method from the `messageExtender` object. Many more custom fields can be added to the same message just by calling the same method with distinct keys (and values of your choice);
* \[5] Adds the image attachment to the message using the `addAttachment` method from the `messageExtender` object. Many attachments can be added all at once using the `addAttachments` method;
* \[6] Finishes the `modifyExtender` object, which is crucial so as to apply the extensions made to the message and make them visible to the user.

### Step 3: Deploy to the server

To deploy the app, run:

```
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

The `<server_url>` parameter is the URL of your Rocket.Chat server. Replace the placeholders with the URL, username, and password for the server. After executing this command, your application will begin to be deployed to the server.

#### Packaging your app

Alternatively, you can execute the `rc-apps package`, which will provide you with a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;

### Step 4: Test the slash command

After the application has been deployed, the slash command `/extend-message` can be executed in any channel.

When the registered slash command is executed, a message will be sent to the current channel and altered to include an image attachment and a custom field. The attached image is visible in the message after editing. In addition, the created custom fields are accessible from any database client of your choosing.\
