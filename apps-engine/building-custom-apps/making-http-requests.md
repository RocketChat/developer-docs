# HTTP Requests

If you want to connect your app to the outside world, the HTTP property enables users to invoke an external web service.

In this topic, we will create a slash command `get` for our [Hello World app](../getting-started/creating-an-app.md). This command executes a `GET` HTTP request based on the given URL. You can also use our [Tester App](https://github.com/RocketChat/Apps.RocketChat.Tester) or any app of your choice. Make sure that a Rocket.Chat server is ready to deploy the app.

### Step 1: Register the Slash Command

The slash command must be registered in the app's main class, at the root of the project.

{% code lineNumbers="true" fullWidth="true" %}
```typescript
import { IAppAccessors, IConfigurationExtend, ILogger } from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { HTTPRequestCommand } from './commands/HTTPRequestCommand'; // [1]

export class HelloWorldApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async extendConfiguration(configuration: IConfigurationExtend) {
        configuration.slashCommands.provideSlashCommand(new HTTPRequestCommand()); // [2]
    }
}
```
{% endcode %}

Here, we import our new slash command class and then register it in the configuration of the app.

### Step 2: Create the Slash Command

1. If you haven't created a separate directory for slash commands, it is recommended to create a `commands` directory at the root of the project.&#x20;
2. Create the `HTTPRequestCommand.ts` file in this directory.&#x20;
3. Then enter the code shown below:

{% code lineNumbers="true" fullWidth="true" %}
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
{% endcode %}

This code implements the following:&#x20;

1. The slash command is called `get`.
2. When executed, it uses the argument that the user passed after the command as the URL.
3. The argument is mandatory. If no argument is provided, an error is thrown.
4. Perform the `GET` request using the provided argument.

Optionally, you can store the `GET` request in a console constant. When the command is executed, it is logged.

{% code lineNumbers="true" %}
```typescript
const response = await http.get(url);
console.log("result: " + response.data);
```
{% endcode %}

### Step 3: Print the Request to a Conversation

Now, instead of logging console output to the instance's log, let's output it to the conversation.

Add the following private method to `HTTPRequestCommand.ts`.

{% code lineNumbers="true" fullWidth="true" %}
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
{% endcode %}

This function implements the following:&#x20;

1. Gets the user who invoked the command (in this case, you).&#x20;
2. Selects the room where the command was executed.&#x20;
3. Sets the received string as the message.&#x20;
4. Sends the message to the room.

Then, append the following code to the end of the executor method:

{% code lineNumbers="true" %}
```typescript
const response = await http.get(url);
const message = JSON.stringify(response.data, null, 2);
await this.sendMessage(context, modify, message);
```
{% endcode %}

Instead of simply sending the request and not capturing the response, we store the response in a constant, format its content as a string, and transmit it using our new `sendMessage` method.

{% hint style="info" %}
**Note:** To learn more about messaging, see the [IMessageBuilder](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_imessagebuilder.imessagebuilder.html) documentation.
{% endhint %}

## Step 4: Deploy the App

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

## Step 5: Test the App

After deploying the application, enter `/get <some_url>` in any channel and the app will send a `GET` request to the specified URL. In this example, we will utilize [JSONPlaceholder](https://jsonplaceholder.typicode.com) to obtain dummy data for testing our application:

* Enter `/get https://jsonplaceholder.typicode.com/todos/1` in a chat.
* You will receive the following response in the chat:

```json
{
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
}
```
