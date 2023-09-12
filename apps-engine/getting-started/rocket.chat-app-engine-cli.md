# Apps Engine CLI

The Rocket.Chat Apps Engine CLI is a simple command-line interface that facilitates the development of Rocket.Chat applications. This computer program allows you to create and delete files, execute programs, and navigate through folders and files. On a Mac, it is referred to as Terminal, whereas on Windows, it is Command Prompt. The Command Line is a potent application that will expand your programming capabilities.

\
Using straightforward commands, you can compile and deploy a basic app structure to your Rocket.Chat Server. We have enhanced its capacity to generate boilerplate code for various functions, display autocomplete installation instructions, submit an app for review in the marketplace, and more. The Rocket.Chat Apps Engine CLI enables you to create new applications and deploy them on your deployment environment, as well as package your application for shipping and future deployment on other installations.

\
The CLI is hosted on [GitHub](https://github.com/RocketChat/Rocket.Chat.Apps-cli) and distributed via [NPM](https://www.npmjs.com/package/@rocket.chat/apps-cli). It provides an easy interface for developing extensions.

## Installing Rocket.Chat Apps Engine CLI

Before installing the CLI, you must ensure that [Node.js is already installed](https://nodejs.org/en) on your system. Use the following command in your terminal to verify the installation of Node.js:&#x20;

```bash
node -v
# v10.15.3
# It should return you a valid version.
```

Run the following command in your terminal after installing Node.js to deploy the CLI globally.

```bash
npm install -g @rocket.chat/apps-cli
```

{% hint style="info" %}
**Troubleshooting Tip**\
\
**Error:** While attempting to execute the preceding command, if your operating system rejects the operation, it is likely that you do not have permission to access the file as the current user. If you suspect a permissions issue, please double-check your NPM installation, or rerun the command as root/Administrator.

\
**Resolution:** Prefix the command with sudo and execute as follows:\


**`sudo npm install -g @rocket.chat/apps-cli`**\
\
After executing this command, enter the system user's password. This will grant the application all necessary permissions, as this command must be executed as an administrator.
{% endhint %}

```bash
rc-apps -v
# @rocket.chat/apps-cli/1.4.0 darwin-x64 node-v10.15.3
```

Depending on the speed of your Internet connection, CLI installation will take some time. After installation, run the following command to verify the installation. Note that the response may differ depending on your system and environment, but it should have a similar appearance.

Additionally, we recommend that you [install Visual Studio Code](https://code.visualstudio.com/download). In addition, a local [development instance](https://docs.rocket.chat/deploy/prepare-for-your-deployment/rapid-deployment-methods/docker-and-docker-compose) of Rocket.Chat must be running on your system.

Open the terminal in Visual Studio and execute the following command:&#x20;

```bash
npm install
```

This installs the Apps-Engine framework/library, allowing applications to recognize Apps-Engine.



You are now all set to develop your first app.
