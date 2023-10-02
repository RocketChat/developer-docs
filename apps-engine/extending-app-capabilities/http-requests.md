# HTTP Requests

This document will explain how to connect your Rocket.Chat application to the outside world. The HTTP property permits users to invoke an external web service. In this article, we will construct a slash command that executes a GET HTTP request based on the supplied parameters. You will require the following:&#x20;

* A Rocket.Chat server to deploy the app to
* Our[ Tester App](https://github.com/RocketChat/Apps.RocketChat.Tester) or a newly created app (of your choice)

### Step 1: Register the slash command

The slash command must be registered in the app's main class, at the root of the project.

```typescript
import { IAppAccessors, IConfigurationExtend, ILogger } from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { HTTPRequestCommand } from './slashcommands/HTTPRequestCommand'; // [1]

export class RocketChatTester extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async extendConfiguration(configuration: IConfigurationExtend) {
        configuration.slashCommands.provideSlashCommand(new HTTPRequestCommand()); // [2]
    }
}
```

Here, we \[1] import our new slash command class and then \[2] register it in the configuration of the application.

### Step 2: Create the slash command

Our command will be referred to as get, so to invoke it from the conversation, simply enter `/get <url>`.

Create a `slashcommand` directory at the root of the project and add the `HTTPRequestCommand.ts` file to it. Then paste the code shown below:

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

export class HTTPRequestCommand implements ISlashCommand {
    public command = 'get'; // [1]
    public i18nParamsExample = '';
    public i18nDescription = '';
    public providesPreview = false;

    public async executor(context: SlashCommandContext, read: IRead, modify: IModify, http: IHttp): Promise<void> {
        const [url] = context.getArguments(); // [2]

        if (!url) { // [3]
            throw new Error('Error!');
        }

        await http.get(url); // [4]
    }
}
```

This code indicates:&#x20;

* \[1] The command will be called get.
* When executed, \[2] it uses the argument that the user passed after the command as the URL.
* \[3] The argument is required
* \[4] Perform the get request using the provided argument.

You can optionally store the `GET` request in a console constant. When the command is executed, it is logged.

```typescript
const response = await http.get(url);
console.log("result: " + response.data);
```

### Step 3: Deploy to the server

To deploy the app, run:&#x20;

```
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

The `<server_url>` parameter is the URL of your Rocket.Chat server. Replace the placeholders with the URL, username, and password for the server. After executing this command, your application will begin to be deployed to the server.

#### Packaging your app

Alternatively, you can execute the `rc-apps package`, which will provide you with a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;

### Step 4: Testing the app by calling the slash command

After deploying the application, you can input `/get some_url>` in any channel and the app will send a `GET` request to the specified URL. In this example, we will utilize [JSONPlaceholder](https://jsonplaceholder.typicode.com) to obtain dummy data for testing our application:

* Enter `/get https://jsonplaceholder.typicode.com/todos/1` in a chat
* Your Rocket.Chat instance will print out to the console the following:\
  `result: {"userId":1,"id":1,"title":"delectus aut autem","completed":false}`

**Note:** If you do not see the result, enable info logs in your instance by selecting "**1 - Errors and Information**" at **Administration** > **Logs** > **Log** **Level**.

### Print the request in the chat&#x20;

Now, instead of logging console output to the instance's log, let's output it to the conversation.

Add the following private method to `HTTPRequestCommand.ts`.

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

\
This function \[1] gets the user who invoked the command (in this case, you), \[2] selects the room where the command was executed, \[3] sets the received string as the message, and \[4] sends the message to the room.\
\
**Note:** To learn more about messaging, please visit the [IMessageBuilder](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_imessagebuilder.imessagebuilder.html) documentation.\
\
Then, append the following code to the end of the executor method:

```typescript
const response = await http.get(url); // [1]
    const message = JSON.stringify(response.data, null, 2); // [2]
    await this.sendMessage(context, modify, message); // [3]
```

Instead of simply sending the request and not capturing the response, we \[1] store the response in a constant, \[2] format its content as a string, and \[3] transmit it using our new `sendMessage` method.

Save the file and redeploy the app by running:

```
rc-apps deploy --url <server_url> -u <user> -p <pwd> --update
```

Now, when you execute the slash command `/get https://jsonplaceholder.typicode.com/todos/1`, you will receive the following response in the chat:

```typescript
{
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
}
```
