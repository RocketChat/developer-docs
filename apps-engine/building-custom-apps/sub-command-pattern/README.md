# Slash Commands

The Slash Commands feature enables users to invoke your app or any other functionality by entering a string in the message composer window. This reduces the amount of text needed to produce complex Markdown. The `SlashCommand` method is used to call an app deployed in Rocket.Chat. Your app can contain numerous slash commands and subcommands.&#x20;

In this section, we'll send a message to any room from our [Hello World app](../../getting-started/creating-an-app.md) using the `slashCommand` property.

For this app, we will create a main slash command called `phone`, and it will have two subcommands: `text` and `call`. We want to execute these subcommands to invoke an application function. We will use them as follows:&#x20;

* `/phone text`&#x20;
* `/phone call`

{% hint style="info" %}
Although it is possible to have everything in a single file, it is not recommended. Put each physical component of your application in its own file, and logically similar components in their own subdirectories. We recommend creating a `commands` subdirectory at the root of your project for slash command-related files, but you are free to choose a different name.
{% endhint %}

### Step 1: Register the Slash Command

{% hint style="info" %}
The following code excerpts are a recommendation for organizing the slash commands in your application. Even if you do not wish to adhere to the subcommand pattern, you must still register the slash command.&#x20;
{% endhint %}

The primary step is to register the slash command. It must be registered in the app's main class, at the project's root.

1. Add the following code to register your slash command, `phone`:

{% code lineNumbers="true" %}
```typescript
public async extendConfiguration(configuration: IConfigurationExtend) {
    configuration.slashCommands.provideSlashCommand(new PhoneCommand());
}
```
{% endcode %}

2. Then, import the new slash command class by adding the following import statements to your file:

{% code lineNumbers="true" %}
```typescript
import { IAppAccessors, IConfigurationExtend, ILogger } from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { PhoneCommand } from './commands/PhoneCommand';
```
{% endcode %}

### Step 2: Create the Slash Command

1. Create a `PhoneCommand.ts` file in the `commands` directory that we created at the root of the project. In this file, the slash command is defined.&#x20;
2. Now add the following code:

{% code lineNumbers="true" %}
```typescript
import {
    IHttp,
    IModify,
    IRead,
} from '@rocket.chat/apps-engine/definition/accessors';
import {
    ISlashCommand,
    SlashCommandContext,
} from '@rocket.chat/apps-engine/definition/slashcommands';

export class PhoneCommand implements ISlashCommand {
    public command = 'phone'; 
    public i18nParamsExample = '';
    public i18nDescription = '';
    public providesPreview = false;

    public async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp): Promise<void> {
        const [subcommand] = context.getArguments(); 

        if (!subcommand) { 
            throw new Error('Error!');
        }

        switch (subcommand) { 
            case 'text': 
                console.log('Texting!');
                break;

            case 'call': 
                console.log('Calling!');
                break;

            default: 
                throw new Error('Error!');
        }
    }
}
```
{% endcode %}

Let's look at the logic of the code in the `PhoneCommand.ts` file:

* The slash command is named `phone`.
* When it gets executed, we get the argument that the user passed after the command. The argument is used as the subcommand and it is mandatory.
* We match the argument with the list of allowed subcommands, in this case, `text` and `call`.
* If the argument matches the `text` subcommand, log **"Texting!"**.
* If the argument matches the `call` subcommand, log **"Calling!"**
* Any other argument throws an error.

### Step 3: Deploy to the Server

After registering and defining your slash command, the final step is to deploy your application to the server.

To deploy the app, run:&#x20;

```bash
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

* The `<server_url>` parameter is the URL of your Rocket.Chat server.&#x20;
* Replace the placeholders with the URL, username, and password for your server, respectively.&#x20;

After executing this command, your application will be deployed to the server.

{% hint style="info" %}
**Packaging your app**

Alternatively, you can execute the `rc-apps package` command. This gives you a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;
{% endhint %}

### Step 4: Testing your New Slash Command

After deploying the application, you can input `/phone text` or `/phone call` on any channel. The app logs `"Texting!"` or `"Calling!"` to the console, respectively.

If you want to send it to the channel, follow these steps:&#x20;

1. Add the following method to the `PhoneCommand` class:

{% code lineNumbers="true" %}
```typescript
private async sendMessage(context: SlashCommandContext, modify: IModify, message: string): Promise<void> {
    const messageStructure = modify.getCreator().startMessage();
    const sender = context.getSender(); 
    const room = context.getRoom();
    
    messageStructure
        .setSender(sender)
        .setRoom(room)
        .setText(message);
    
    await modify.getCreator().finish(messageStructure);
}
```
{% endcode %}

This function:&#x20;

* Retrieves the user who invoked the command (in this case, you).
* Selects the room where the command was executed.
* Sets the received string as the message.
* Sends the message to the room.

2. Change the `console.log` from the switch block of the executor method and call the `sendMessage` method instead:

{% code lineNumbers="true" %}
```typescript
case 'text':
    await this.sendMessage(context, modify, 'Texting!');
    break;

case 'call':
    await this.sendMessage(context, modify, 'Calling!');
    break;
```
{% endcode %}

Here, `context` and `modify` are the arguments passed to the executor method, and they are forwarded to the `sendMessage` method.

3. Save the file and redeploy the app by running the following command:

```bash
rc-apps deploy --url <server_url> -u <user> -p <pwd> --update
```

All that's left is for you to test it! Go to the channel in Rocket.Chat where you want to test your app by typing `/phone text` and `/phone call` in the message composer. Press **Enter** and you can see the output as `Texting!` or `Calling!` in the channel.

Similarly, you can register and define multiple slash commands for your app that are tailored to your organization's requirements. In addition to slash commands, you can use other properties supported by the Apps-Engine to expand the functionality of your application to meet business requirements.&#x20;

Once the app has been developed and deployed to the Rocket.Chat server, it undergoes multiple stages. To learn more, see the [App Lifecycle](../../understanding-app-lifecycle.md) section.
