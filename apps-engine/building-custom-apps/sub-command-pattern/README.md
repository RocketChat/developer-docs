# Slash Commands

Logging to the console is satisfactory, but we need our application to interact with Rocket.Chat rooms. In this section, we'll send a message to any room from our Hello World app. Using the `slashCommands` property, let's add a slash command to the Hello World app we created in the previous section.&#x20;

A Slashcommand is a method for calling an application deployed in Rocket.Chat. Your application can contain numerous slash commands and subcommands.

For this application, let's create the `/phone` command with the subcommands `/text` and `/call`. Therefore, you should be able to execute these subcommands to invoke an application function. The name of our main command will be phone, and it will have two subcommands: `text` and `call`. We will use them as follows:&#x20;

* `/phone text`&#x20;
* `/phone call`

Although it is possible to have everything in a single file, it is not recommended. Put each physical component of your application in its own file, and logically similar components in their own subdirectories.

We recommend creating a `commands` subdirectory at the root of your project for slash command-related files, but you are free to choose a different name.

### Step 1: Register the slash command

The following code excerpts are a recommendation for organizing the slash commands in your application. Even if you do not wish to adhere to the subcommand pattern, you must still register the slash command.&#x20;

The primary step is to register the slash command. It must be registered in the app's main class, at the project's root. \


Execute the following command to register your slash command, `phone`:

```typescript
public async extendConfiguration(configuration: IConfigurationExtend) {
configuration.slashCommands.provideSlashCommand(new PhoneCommand());
}
```

Then, import the new slash command class by executing the following:

```typescript
import { IAppAccessors, IConfigurationExtend, ILogger } from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { PhoneCommand } from './slashcommands/PhoneCommand';
```

## Step 2: Create the slash command

\
The following step is to create the slash command.&#x20;

First, create a `PhoneCommand.ts` file in the `slashcommands` directory at the root of the project. In this file, the slash command is defined. Now add the code below:

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
    public command = 'phone'; // [1]
    public i18nParamsExample = '';
    public i18nDescription = '';
    public providesPreview = false;

    public async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp): Promise<void> {
        const [subcommand] = context.getArguments(); // [2]

        if (!subcommand) { // [3]
            throw new Error('Error!');
        }

        switch (subcommand) { // [4]
            case 'text': // [5]
                console.log('Texting!');
                break;

            case 'call': // [6]
                console.log('Calling!');
                break;

            default: // [7]
                throw new Error('Error!');
        }
    }
}
```

What this code tells us:

* \[1] I want my command to be called phone.
* When it gets executed, \[2] I want to get the argument the user passed after the command and to use it as the subcommand.
* \[3] The argument is mandatory
* \[4] Try to match the argument in the list of allowed subcommands
* \[5] If text matches, log "Texting!"
* \[6] If call matches, log "Calling!"
* \[7] If anything else will throw an error

After registering and defining your slash command, the final step is to deploy your application to the server.&#x20;

### Step 3: Deploy to the server

\
To deploy the app, run:&#x20;

```
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

The `<server_url>` parameter is the URL of your Rocket.Chat server. Replace the placeholders with the URL, username, and password for the server. After executing this command, your application will begin to be deployed to the server.

#### Packaging your app

Alternatively, you can execute the `rc-apps package`, which will provide you with a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;

### Step 4: Testing your new slash command

After deploying the application, you can input `/phone text` or `/phone call` on any channel to have the app output `"Texting!"` or `"Calling!"` to the console, respectively.

This command outputs the specified text to the console. If you wish to publish it in the channel, please follow the below instructions.&#x20;

Add the following method to the `PhoneCommand` class:

```typescript
private async sendMessage(context: SlashCommandContext, modify: IModify, message: string): Promise<void> {
const messageStructure = modify.getCreator().startMessage();
const sender = context.getSender(); // [1]
const room = context.getRoom(); // [2]

messageStructure
.setSender(sender)
.setRoom(room)
.setText(message); // [3]

await modify.getCreator().finish(messageStructure); // [4]
}

```

This function \[1] retrieves the user who invoked the command (in this case, you), \[2] selects the room where the command was executed, \[3] sets the received string as the message, and \[4] sends the message to the room.

Then, change the `console.log` from the switch block of the executor method and call the `sendMessage` method instead:

```typescript
case 'text':
        await this.sendMessage(context, modify, 'Texting!');
        break;

    case 'call':
        await this.sendMessage(context, modify, 'Calling!');
        break;
```

Note: `context` and `modify` are the arguments passed to the executor method, and they will be forwarded to the `sendMessage` method.

Save the file and redeploy the app by running:

```
rc-apps deploy --url <server_url> -u <user> -p <pwd> --update
```

All that's left is for you to test it! Head over to the channel in Rocket.Chat to test your app by typing `/text` and `/call` in the message composer.&#x20;

Similarly, you can register and define multiple slash commands for your app that are tailored to your organization's requirements. The Slash Commands feature enables users to invoke your app or any other functionality by entering a string into the message composer window. By reducing the amount of text needed to produce complex Markdown, slash commands can save time.

In addition to slash commands, you can use the other properties supported by the Apps Engine to expand the functionality of your application to meet business requirements.&#x20;

Once the application has been developed and deployed to the Rocket.Chat server, undergoes multiple stages. Visit the App Lifecycle section to learn more about the app development lifecycle and the lifecycle of a Rocket.Chat server app.&#x20;
