# Apps-Engine CLI

The Rocket.Chat Apps-Engine CLI is a simple command-line interface that facilitates the development of Rocket.Chat applications. This computer program allows you to create and delete files, execute programs, and navigate through folders and files. On a Mac, it is referred to as Terminal, whereas on Windows, it is Command Prompt. The Command Line is a potent application that will expand your programming capabilities.

The CLI is hosted on [GitHub](https://github.com/RocketChat/Rocket.Chat.Apps-cli) and distributed via [NPM](https://www.npmjs.com/package/@rocket.chat/apps-cli). It provides an easy interface for developing extensions.&#x20;

## Installing Rocket.Chat Apps-Engine CLI

1. Before installing the CLI, you must ensure that [Node.js is installed](https://nodejs.org/en) on your system. Use the following command in your terminal to verify the installation of Node.js. This returns a valid version of Node.js, for example, `v10.15.3`:

```bash
node -v
```

2. After installing Node.js, run the following command in your terminal to deploy the CLI globally.

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

3. After installation, run the following command to verify the installation. Note that the response may differ depending on your system and environment, but it should have a similar appearance. For example, `@rocket.chat/apps-cli/1.4.0 darwin-x64 node-v10.15.3`

```bash
rc-apps -v
```

4. Next, install the Apps-Engine framework/library which allows applications to recognize Apps-Engine. To do this, open the terminal in Visual Studio and execute the following command:&#x20;

```bash
npm install
```

You are now all set to develop your first app.
