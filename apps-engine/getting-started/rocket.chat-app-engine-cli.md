---
description: >-
  This guide will help you get started with our official Apps-Engine Command
  Line Interface (CLI)  to start creating your own apps.
---

# The Apps-Engine CLI

The Rocket.Chat Apps-Engine CLI is a simple Command Line Interface, that gives you a kickstart in developing your Rocket.Chat App.

Using simple commands, you can create a basic app structure and package & deploy it into your RC Server. We have extended its capability to generate boilerplate code for various functions, display autocomplete installation instructions, submit an App to the Marketplace for review, and more.

The CLI is available on [GitHub](https://github.com/RocketChat/Rocket.Chat.Apps-cli) and published on [NPM](https://www.npmjs.com/package/@rocket.chat/apps-cli). It provides an easy interface for developing extensions. Follow the quick steps below to create your first application.

## Installation

Before installing the CLI, ensure that you have [Node](https://nodejs.org/en/) already installed on your machine. To verify Node installation, use the following command in your terminal.

```bash
node -v
# v10.15.3
# It should return you a valid version.
```

Once you have installed Node, run the following command in your terminal to install the CLI globally.

```bash
npm install -g @rocket.chat/apps-cli
```

Depending on your internet connection, installing the CLI will take a while. After installation, run the following command to verify the installation.

```bash
rc-apps -v
# @rocket.chat/apps-cli/1.4.0 darwin-x64 node-v10.15.3
```

Note that the response may vary depending on your machine and environment, but it should look similar. Now, you are all set to create your first app.

## App Development using CLI

### Logging Inside an App

Due to limitations of NodeJS's `vm` the package, we have had to implement a custom logger class. To make usage of this you can use `this.getLogger()` and then do the normal `console` style logging.

### `rc-apps create`

The development tools provide a command to quickly scaffold a new Rocket.Chat App, run `rc-apps create` and a new folder will be created inside the current working directory with a basic App which does nothing but will compile and be packaged in the `dist` folder.

### App description

The app description file, named `app.json`, contains basic information about the app. You can check the [app-schema.json](https://github.com/RocketChat/Rocket.Chat.Apps-engine/blob/master/src/definition/app-schema.json) file for all the detailed information and fields allowed in the app description file, the basic structure is similar to this:

```json
{
    "id": "5cb9a329-0613-4d39-b20f-cc2cc9175df5",
    "name": "App Name",
    "nameSlug": "app-name",
    "version": "0.0.1",
    "requiredApiVersion": "^1.4.0",
    "description": "App which provides something very useful for Rocket.Chat users.",
    "author": {
        "name": "Author Name <author@email.com>",
        "support": "Support Url or Email"
    },
    "classFile": "main.ts",
    "iconFile": "beautiful-app-icon.jpg"
}
```

### Extending the App class

The basic creation of an App is based on extending the `App` class from the Rocket.Chat Apps _definition_ library. Your class also has to implement the constructor and optionally the `initialize` function. For more details on it check the [App definition documentation](https://rocketchat.github.io/Rocket.Chat.Apps-engine/classes/app.app-1.html).

```ts
import {
    IAppAccessors,
    IConfigurationExtend,
    IEnvironmentRead,
    ILogger,
} from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';

export class TodoListApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async initialize(configurationExtend: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
        await this.extendConfiguration(configurationExtend, environmentRead);
        this.getLogger().log('Hello world from my app');
    }
}
```

### Packaging the app

Currently, the Rocket.Chat servers and Marketplace allow submission of zip files, these files can be created by running `rc-apps package` which packages your app and creates the zip file under `dist` folder.

### Uploading the app

For uploading the app you need to add the required parameters in the `.rcappsconfig` already created in the apps directory. It accepts two types of objects:-

* Upload using username, password

```js
{
    url: string;
    username: string;
    password: string;
}
```

* Upload using personal access token and userId

```
{
    url: string;
    userId: string;
    token: string;
}
```

### Enabling autocomplete for commands

To enable autocomplete for the apps cli use the command `rc-apps autocomplete <your-shell-type>` with the shell type as `zsh` or `bash` as the supported types. This would provide step-by-step instructions to enable shell completion in your preferred shell.
