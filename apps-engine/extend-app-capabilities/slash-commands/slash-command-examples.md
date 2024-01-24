# Slash Command Examples

In this section, we'll look at two slash command examples:

* Update user status value and text.
* Extend messages to include an image attachment and custom field.

## Update user status&#x20;

To update the user status, we will create a new slash command that takes two parameters:&#x20;

* The first parameter is the status value - online, away, busy, etc.
* The second contains the status text.&#x20;

We will refer to the status slash command as `st` to execute code such as:

```
/st away Doing code :)
```

### Step 1: Create the slash command

To implement this, follow these steps:

1. Create a new class named `StatusUpdateCmd.ts` and place it in the same subdirectory `commands` that we created in the [previous section](./).
2. Now, add the following code for the status update:&#x20;

{% code overflow="wrap" lineNumbers="true" fullWidth="true" %}
```typescript
import {
    IHttp,
    IModify,
    IPersistence,
    IRead,
} from '@rocket.chat/apps-engine/definition/accessors';
import { IRoom } from '@rocket.chat/apps-engine/definition/rooms';
import {
    ISlashCommand,
    SlashCommandContext,
} from '@rocket.chat/apps-engine/definition/slashcommands';
import { IUser } from '@rocket.chat/apps-engine/definition/users';

export class StatusUpdateCmd implements ISlashCommand {
   public command = 'st';
   public i18nParamsExample: string = 'status_update_command_params_example';
   public i18nDescription: string = 'status_update_command_description';
   public providesPreview: boolean = false;
   
   public async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp, persis: IPersistence): Promise<void> {
       const user = context.getSender();
       const params = context.getArguments();
       const room: IRoom = context.getRoom();
       
       if (!params || params.length == 0) {
           return notifyMessage(room, read, user, "At least one status argument is mandatory. A second argument can be passed as status text.");
       }
       
       let status = params[0];
       let statusText = params.length > 1 ? params.slice(1).join(' ') : '';
       
       await modify.getUpdater().getUserUpdater().updateStatus(user, statusText, status);
       await notifyMessage(room, read, user, "Status updated to " + status + " (" + statusText + ").");
   }
   
   private async notifyMessage(room: IRoom, read: IRead, sender: IUser, message: string): Promise<void> {
       const notifier = read.getNotifier();
       const messageBuilder = notifier.getMessageBuilder();
       messageBuilder.setText(message);
       messageBuilder.setRoom(room);
       return notifier.notifyUser(sender, messageBuilder.getMessage());
    }
}
```
{% endcode %}

Here, we are implementing the following:

* Fetch the status value from the first argument. This argument is mandatory otherwise, the `notifyMessage` method informs the user that the argument is missing.
* Fetch the status message from the second argument, joining the terms with a white space. If the second argument is not passed, the status message remains an empty string.
* Update the status according to the value passed using `modify`.
* Notify the user about the status update.

### Step 2: Register the slash command

In the app's main class, register the new slash command as follows:

```typescript
public async extendConfiguration(configuration: IConfigurationExtend) {
        configuration.slashCommands.provideSlashCommand(new StatusUpdateCmd());
}
```

Make sure to import the slash command class in the main class:

```typescript
import { StatusUpdateCmd } from './commands/StatusUpdateCmd';
```

All that remains is deployment and testing!

### Step 3: Deploy the app

In the command line, go to the app folder and run:&#x20;

```
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

* The `<server_url>` parameter is the URL of your Rocket.Chat server.&#x20;
* Replace the placeholders with the URL, username, and password for your server, respectively.&#x20;

After executing this command, your application will be deployed to the server.

{% hint style="info" %}
**Packaging your app**

Alternatively, you can execute the `rc-apps package` command. This gives you a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;
{% endhint %}

### Step 4: Test the app

Send `/st <status> <message>` to any channel. You can see the change in the user status accordingly.

<figure><img src="https://lh4.googleusercontent.com/XJs5iHML3qvpXmlMm7arHQrLHxLSH1utsMnZozAA0-fsoYAUdFvOLj80yA7T7HLLEQKn7ZPj4uICWblde2JINJ3v8JQ62ln4lsqhzEsQZce8yvI3Gnmwkzh6pPHiUGyhR3-tl_q0lZPChZztDArs5mM" alt=""><figcaption></figcaption></figure>

If we execute `/st` with no input, we receive the notification:

<div align="left">

<figure><img src="https://lh4.googleusercontent.com/p5BjJCHrjp8fP8EfiambuJsd-gnMAHVJpaSbTRKtFNLFhk9RpCq7UVN-49XKU0LbYT9Yl00crxFdAYLvqmxYwSndJrEgyJC8phsIO4yib7rgtphqeGL8Bnurg7IoMADzncAsyTLz7SuyRTNRifz57jI" alt=""><figcaption></figcaption></figure>

</div>

## Extend messages

This example explains how to modify messages to include custom fields and attachments. We will construct an app that is invoked via a slash command, sends a message, and is extended to include an image and a custom field.&#x20;

### Step 1: Add attachments&#x20;

Rocket.Chat supports numerous attachments (and applicable customizations for these attachments). For instance, you can attach images, documents, videos, and audio files to messages. The first step in doing so is to create your own attachment class.

In this approach, we will implement the `ImageAttachment` class in the project's root as follows:

{% code lineNumbers="true" %}
```typescript
import { IMessageAttachment } from '@rocket.chat/apps-engine/definition/messages';

export class ImageAttachment implements IMessageAttachment{
    imageUrl?: string;

    constructor(imgUrl: string){
        this.imageUrl = imgUrl;
    }
}
```
{% endcode %}

Here, we use a class attribute with the same identifier and type as in the `IMessageAttachment` interface, which is required for your linked media to be visible to the user. This is because only the variables in your attachment class defined in the `IMessageAttachment` interface will be used to retrieve the attachment's media.

You can also construct your own classes for video or audio attachments, or you can group them all into a single class that can accommodate all of these possibilities. Make sure to use the same attributes described in the `IMessageAttachment.d.ts` file.

{% hint style="info" %}
The audio and video formats that are supported in the Rocket.Chat message attachments are identical to HTML audio and video elements.
{% endhint %}

### Step 2: Create the slash command

To implement this, follow these steps:

1. Create a new class named `ExtendMessageCommand.ts` and place it in the same subdirectory `commands` that we created in the [previous section](./).
2. Now, add the following code:&#x20;

{% code overflow="wrap" lineNumbers="true" fullWidth="true" %}
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
}

```
{% endcode %}

The main actions performed by the code above are:

* \[1] Sends a message and stores the sent message's ID in the `messageId` variable.
* \[2] Uses the sent message's ID. The `messageExtender` object is returned by the `getMessageExtender` method and stored in the `messageExtender` variable.
* \[3] Creates the attachment object as an instance of the `ImageAttachment` class. Here, the attachment is an image.
* \[4] Adds a custom field with the key '`key`' linked to the `value` using the `addCustomField` method from the `messageExtender` object. Many more custom fields can be added to the same message by calling the same method with distinct keys (and values of your choice).
* \[5] Adds the image attachment to the message using the `addAttachment` method from the `messageExtender` object. Many attachments can be added all at once using the `addAttachments` method.
* \[6] Finishes the `modifyExtender` object, which is crucial to apply the extensions made to the message and make them visible to the user.

#### Custom Fields

Custom fields are structures linked to messages in which each field is organized as if it were an entry in a dictionary. That is, each field must contain a key and corresponding value. These elements are retained in the server's database along with the corresponding messages so that they can be retrieved later.

### Step 3: Create auxiliary methods&#x20;

It is beneficial to define a few additional methods within our slash command class so that our code remains concise and straightforward.

**Method: `sendMessage`**

The `sendMessage` method needs to return the message's ID after it has been sent. The method must now return a `Promise<string>` as opposed to a `Promise<void>`.

The modified `sendMessage` method is shown below:

{% code overflow="wrap" lineNumbers="true" fullWidth="true" %}
```typescript
private async sendMessage(context: SlashCommandContext, modify: IModify, message: string): Promise<string> {
    const messageStructure = modify.getCreator().startMessage();
    const sender = context.getSender();
    const room = context.getRoom();

    messageStructure
        .setSender(sender)
        .setRoom(room)
        .setText(message);

    return modify.getCreator().finish(messageStructure); // [1]
}
```
{% endcode %}

**Method: `getMessageExtender`**

After obtaining the message's ID, we can get the `messageExtender` object, which enables the addition of custom fields and attachments.

To obtain the `messageExtender` object, use the following asynchronous method in the slash command class:

{% code overflow="wrap" lineNumbers="true" fullWidth="true" %}
```typescript
private async getMessageExtender(context: SlashCommandContext, modify: IModify, messageId: string): Promise<IMessageExtender>{
    const sender = context.getSender();
    return modify.getExtender().extendMessage(messageId, sender); // [1]
}
```
{% endcode %}

Here, we use the message's ID returned by the `sendMessage` method to obtain the `messageExtender` object using the `modifyExtender` object.

After creating the methods, you only need to invoke them with a slash command.

### Step 4: Register the slash command

We must register the slash command in the app's main class, the project's root.

{% code overflow="wrap" lineNumbers="true" %}
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
{% endcode %}

Here, we import our new slash command class and register it in the app's configuration.&#x20;

### Step 5: Deploy the app

To deploy the app, follow [#step-3-deploy-the-app](slash-command-examples.md#step-3-deploy-the-app "mention")from the previous example.

### Step 6: Test the slash command

After the app has been deployed, execute the slash command `/extend-message` in any channel.

When you execute the registered slash command, a message is sent to the current channel and altered to include an image attachment and a custom field. The attached image is visible in the message after editing. In addition, the created custom fields are accessible from any database client of your choosing.
