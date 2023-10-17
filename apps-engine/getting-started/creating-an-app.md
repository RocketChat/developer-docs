# Creating Apps

Now, that you've understood the basic concepts of the Apps Engine and installed the CLI, you can create an extremely basic Rocket.Chat App and test it out to understand things. To get started, just recall the commands inside the Apps Engine CLI.

`rc-apps` is a command-line interface (CLI) utility that facilitates the app development process by providing commands to rapidly scaffold an Rocket.Chat application. Once you initiate rc-apps in your terminal, you will be presented with a list of commands that you can execute as needed. Here is a list of commands that Rocket.Chat Apps Engine supports:&#x20;

<table><thead><tr><th width="204.5">Command</th><th>Purpose</th></tr></thead><tbody><tr><td><code>autocomplete</code></td><td>Automatically displays installation instructions</td></tr><tr><td><code>create</code></td><td>Facilitates a simplified way of creating an app</td></tr><tr><td><code>deploy</code></td><td>Allows app deployment to the server</td></tr><tr><td><code>generate</code></td><td>Adds boilerplate code for numerous functions</td></tr><tr><td><code>help</code></td><td>Display help for <code>rc-apps</code></td></tr><tr><td><code>login</code></td><td>Provides the steps for logging into Rocket.Chat Cloud</td></tr><tr><td><code>logout</code></td><td>Revokes the Rocket.Chat cloud credentials</td></tr><tr><td><code>package</code></td><td>Packages the app for distribution</td></tr><tr><td><code>submit</code></td><td>Submits an app to the marketplace for review</td></tr><tr><td><code>watch</code></td><td>Monitors app changes and redeploys the modified app to the server</td></tr></tbody></table>

Now let's build our initial application, **Hello World!**&#x20;

### Step 1: Execute the create command

Now, to create a new app, execute `rc-apps create`, and a new folder containing a simple app that will only compile and be packaged in the `dist` folder will be created in the current working directory.&#x20;

### Step 2: Provide app details

You will be required to provide the following app details:

* App Name
* App Description
* Author’s Name&#x20;
* Author’s Home Page&#x20;
* Author’s Support Page

{% hint style="info" %}
**Troubleshooting tip**

\
If you receive the error message '**TypeError: Cannot read properties of undefined \[reading 'message']**', do not be alarmed. You can disregard this and use the `cd test` command to determine if a folder for your application was created in Visual Studio.&#x20;
{% endhint %}

### Step 3: Open the app folder in Visual Studio

1. Now, launch **Visual Studio** > select **Open Folder** from the sidebar on the left. You will be able to locate the application folder you provided in the previous step.
2. Select the **app folder.** Once a folder has been **uploaded**, its contents will be displayed in the sidebar.&#x20;
3. Choose the file with the **.ts extension**. This is where all application coding happens.

### Step 4: Comprehend the structure of an app

The app manifest file, `app.json`, contains basic details about the app.&#x20;

Let's examine the `app.json` file for our `HelloWorld` application to comprehend its structure.

```json
{
    "id": "28d63257-94c3-40e8-83eb-9581244598b6",
    "version": "0.0.1",
    "requiredApiVersion": "^1.4.0",
    "iconFile": "icon.png",
    "author": {
        "name": "Pavithra",
        "homepage": "rocketchat.com",
        "support": "support@rocketchat.com"
    },
    "name": "Hello World",
    "nameSlug": "hello-world",
    "classFile": "HelloWorldApp.ts",
    "description": "A basic app that prints Hello World!"
}
```

A Rocket.Chat app is essentially a TypeScript project that contains a main file with a class extending the main `App` class from the Apps Engine. The identity of this file can be found in the `classFile` property of your `app.json` file. The `HelloWorld.ts` TypeScript file should be located. Open the file `HelloWorld.ts`.

{% code lineNumbers="true" %}
```typescript
export class HelloWorldApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }
}
```
{% endcode %}

The first thing you might observe is that the class name and filename are identical. This is intentional; either use the same name for the class and the file in order for the application to compile successfully, or export the primary app class by default as shown below.

```typescript
export default class HelloWorldApp extends App {
    // ...
}
```

For a functioning app, you must define a constructor for access to a large number of parent properties. The constructor accepts three arguments, which are:

1. An `IAppInfo` object: This object contains fundamental information about your application, such as its name, version, description, etc. It is private to the `App` class, but its properties are accessible through multiple get methods.
2. An `ILogger` object: This object is the interface for logging. The `getLogger()` method allows access to this object from within a child class.
3. An `IAppAccessors` object: This object contains all app accessors. This can be accessed via the `getAccessors()` method in the child class.

### Step 5: Develop the app functionality and implement the required cod

As an illustration, let's have the application record "Hello World" in the Rocket.Chat administration interface.&#x20;

To log data, you must first have access to the logger, or more precisely, an object of type `ILogger`. The parent class logs data to the administration interface using an `ILogger` object. We only require access to this object. Unfortunately, since the logger object is private to the `App` class, `this` cannot be used to access it directly.

This can easily be remedied by using the `getLogger` method provided by the `App` class.  Simply store the logger as a separate object, and it can be reused whenever necessary.

{% code overflow="wrap" lineNumbers="true" %}
```typescript
export class HelloWorldApp extends App {
    private readonly appLogger: ILogger
    
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors)
        this.appLogger = this.getLogger()
    }
}
```
{% endcode %}

We have just stored the accessor for the log file in the `appLogger` variable. Now, we can record anything with it. Add the line shown below to the constructor.

```typescript
this.appLogger.debug('Hello, World!')
```

### Step 6: Deploy to the server

To deploy the app, run:&#x20;

```sh
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

The `<server_url>` parameter is the URL of your Rocket.Chat server. Replace the placeholders with the URL, username, and password for the server. After executing this command, your application will begin to be deployed to the server.\


**Packaging your app**

Alternatively, you can execute the `rc-apps package`, which will provide you with a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;

### Step 7: Test the app

To test your app, you need a Rocket.Chat server running locally on your machine and the credentials of an administrator user.

{% hint style="info" %}
In older versions of Rocket.Chat, you might need to turn own **Apps Development Mode** for manual installations to be allowed.

To run Rocket.Chat in develop mode, refer to the document Installing Rocket.Chat for Developing. Enable Apps development mode by navigating to **Administration** > **General** > **Apps**, and clicking the `True` radio button next to **Enable development mode**.
{% endhint %}

The function of the application in this example was to log Hello World to the console. In order to test the app's functionality, we must examine the app logs. Follow the steps below to examine the logs and test the application:&#x20;

1. Login to your Rocket.Chat workspace as an admin.&#x20;
2. Navigate to the **Administration** **Panel** > under **Apps** > select **Marketplace** > search for **HelloWorld** app.&#x20;
3. Click on the **3-dot button** on the right-hand side of the app > from the **menu**, click on **Logs**.&#x20;
4. Scroll down until you see ‘**constructor**’. Click on it, and you will be able to see the message ‘**Hello, World!**’ logged in the console.&#x20;

Congrats, you just created your first app —  a simple Hello World app!

