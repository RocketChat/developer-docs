# Creating Apps

On this page, you will learn about the Apps-Engine commands and create a basic app.

### Apps-Engine CLI Commands

`rc-apps` is a command-line interface (CLI) utility that provides commands to rapidly develop a Rocket.Chat application. Initiate `rc-apps` in your terminal to view the list of commands that you can execute as needed.&#x20;

Here is a list of commands that Rocket.Chat Apps-Engine supports:&#x20;

<table><thead><tr><th width="204.5">Command</th><th>Description</th></tr></thead><tbody><tr><td><code>autocomplete</code></td><td>Automatically displays installation instructions.</td></tr><tr><td><code>create</code></td><td>Simplifies the process of creating an app.</td></tr><tr><td><code>deploy</code></td><td>Deploys an app to the server.</td></tr><tr><td><code>generate</code></td><td>Adds boilerplate code for numerous functions.</td></tr><tr><td><code>help</code></td><td>Displays help for <code>rc-apps</code>.</td></tr><tr><td><code>login</code></td><td>Provides the steps for logging into Rocket.Chat Cloud.</td></tr><tr><td><code>logout</code></td><td>Revokes the Rocket.Chat Cloud credentials.</td></tr><tr><td><code>package</code></td><td>Packages the app for distribution.</td></tr><tr><td><code>submit</code></td><td>Submits an app to the marketplace for review.</td></tr><tr><td><code>watch</code></td><td>Monitors app changes and redeploys the modified app to the server.</td></tr></tbody></table>

### Create a Basic App

Now that you've understood the basic concepts of the Apps-Engine and installed the CLI, let's build our initial app `Hello World`.&#x20;

{% hint style="info" %}
Make sure that you have the [setup environment](./) ready.
{% endhint %}

#### Step 1: Execute the create command

To create a new app, in the command line, execute `rc-apps create`. &#x20;

Enter the following app details:

* **App Name:** `Hello World`
* **App Description:** `A basic app that prints Hello World!`
* **Author’s Name:** `John`
* **Author’s Home Page:** `rocketchat.com`
* **Author’s Support Page:** `support.rocketchat.com`

A folder with the app name is created in the current working directory. The folder contains a simple app that will only compile and be packaged in the `dist` folder.

{% hint style="info" %}
**Troubleshooting tip**

If you receive the error message '**TypeError: Cannot read properties of undefined \[reading 'message']**', do not be alarmed. You can disregard this and use the `cd test` command to determine if a folder for your application was created in Visual Studio.&#x20;
{% endhint %}

#### Step 2: Open the app folder in Visual Studio

1. Launch **Visual Studio** and select **Open Folder** from the sidebar on the left.&#x20;
2. Select the app folder that was created in the previous step.
3. Once the folder has been uploaded, its contents will be displayed in the sidebar.&#x20;

#### Step 3: Comprehend the structure of an app

* The app manifest file `app.json` contains basic details about the app:

```json
{
    "id": "28d63257-94c3-40e8-83eb-9581244598b6",
    "version": "0.0.1",
    "requiredApiVersion": "^1.4.0",
    "iconFile": "icon.png",
    "author": {
        "name": "John",
        "homepage": "rocketchat.com",
        "support": "support@rocketchat.com"
    },
    "name": "Hello World",
    "nameSlug": "hello-world",
    "classFile": "HelloWorldApp.ts",
    "description": "A basic app that prints Hello World!"
}
```

* A Rocket.Chat app is a TypeScript project that contains a main file with a class extending the main `App` class from the Apps-Engine. The identity of this file can be found in the `classFile` property of your `app.json` file. For this example, locate and open the `HelloWorldApp.ts` TypeScript file.
* The following code snippet shows the class in the `HelloWorldApp.ts` file:

{% code lineNumbers="true" %}
```typescript
export class HelloWorldApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }
}
```
{% endcode %}

* Observe that the class name and filename are identical. This is intentional. You can either use the same name for the class and the file for the application to compile successfully, or export the primary app class by default as shown below:

```typescript
export default class HelloWorldApp extends App {
    // ...
}
```

* For a functioning app, you must define a constructor to access a large number of parent properties. The constructor accepts three arguments:
  * **An `IAppInfo` object:** This object contains fundamental information about your application, such as its name, version, description, etc. It is private to the `App` class, but its properties are accessible through multiple GET methods.
  * **An `ILogger` object:** This object is the interface for logging. The `getLogger()` method allows access to this object from within a child class.
  * **An `IAppAccessors` object:** This object contains all app accessors. This can be accessed via the `getAccessors()` method in the child class.

#### Step 4: Implement the app functionality

For this example, the app records "Hello, World!" in the Rocket.Chat administration interface.&#x20;

To log data, you must first have access to the logger, that is, an object of type `ILogger`. The parent class logs data to the administration interface using an `ILogger` object. We only require access to this object. Since the logger object is private to the `App` class, the `this` keyword cannot be used to access it directly.

To resolve this, use the `getLogger` method provided by the `App` class. You need to store the logger as a separate object and it can be reused whenever necessary.&#x20;

Modify the class in the `HelloWorldApp.ts` file as follows:

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

We have just stored the accessor for the log file in the `appLogger` variable. Now, we can record anything with it. Add the line shown below to the constructor and save the file.

```typescript
this.appLogger.debug('Hello, World!')
```

#### Step 5: Deploy to the server

To deploy the app, run:&#x20;

```sh
rc-apps deploy --url <server_url> -u <user> -p <pwd>
```

* The `<server_url>` parameter is the URL of your Rocket.Chat server.&#x20;
* Replace the placeholders with the URL, username, and password for your server, respectively.&#x20;

After executing this command, your application will be deployed to the server.

{% hint style="info" %}
**Packaging your app**

Alternatively, you can execute the `rc-apps package` command. This gives you a compressed zip file of your app that you can upload as a private app to your Rocket.Chat server.&#x20;
{% endhint %}

#### Step 7: Test the app

To test your app, you need a Rocket.Chat server running locally on your machine and the credentials of an administrator user.

{% hint style="info" %}
In older versions of Rocket.Chat, you might need to enable Apps development mode for manual installations to be allowed.&#x20;

To enable Apps development mode:&#x20;

* Go to **Administration** > **General** > **Apps**.
* Click `True` next to **Enable development mode**.

To run Rocket.Chat in develop mode, see [Development Environment Setup](../../getting-started/development-environment-setup.md).&#x20;
{% endhint %}

In this example, the function of the application is to log `Hello, World!` to the console. To test the app's functionality, we must examine the app logs.&#x20;

Follow these steps to examine the logs:&#x20;

1. Login to your Rocket.Chat workspace as an admin.&#x20;
2. Navigate to the **Administration** **Panel**.&#x20;
3. Under **Apps**, select **Marketplace**. Search for the **Hello World** app.&#x20;
4. Click on the 3 dots icon on the right-hand side of the app. From the menu, click on **View Logs**.&#x20;
5. The **App Info** page opens on the **Logs** tab. Scroll down until you see the `"constructor"` expandable section. Select it and you can see the message `"Hello, World!"` logged in the console.&#x20;

Congrats, you just created your first app —  a simple Hello World app!
