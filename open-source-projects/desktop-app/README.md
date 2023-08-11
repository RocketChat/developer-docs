# Desktop App

As a developer, crafting a communication tool that seamlessly aligns with your team's unique requirements can significantly boost productivity and collaboration. The Rocket.Chat desktop app is an open-source project that offers a customizable platform to tailor your communication needs. In this guide, we'll take you through the streamlined process of setting up and building your very own Rocket.Chat Desktop app directly from the source code.

The Rocket.Chat multiplatform client desktop app is built with Electron, a robust framework that empowers developers to create cross-platform applications using web technologies. Setting up the development environment requires you to download and install multiple dependencies.&#x20;

{% hint style="warning" %}
Please maintain an active internet connection throughout the installation process.
{% endhint %}

### Requirements

Before you begin with the installation, make sure you have the following on your machine:

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [node-gyp](https://github.com/nodejs/node-gyp#installation)
* [Yarn](http://yarnpkg.com/) is recommended instead of npm.

## Set up Rocket.Chat Desktop App

**Fetch the code**

* Navigate to your working directory in the terminal and clone the [Github repository](https://github.com/RocketChat/Rocket.Chat.Electron) by executing this command:

```
git clone https://github.com/RocketChat/Rocket.Chat.Electron.git
```

* Navigate to the cloned repository directory, install the project dependencies, and start the project with these commands:

```
cd Rocket.Chat.Electron
yarn
yarn start
```

Once the project is running succesfully,, a Rocket.Chat desktop app window will launch, prompting you to input your server details to initiate the setup process.

**Project Structure**

The source code for the Rocket.Chat Desktop app is located in the `src` folder. When you run the app with the command `yarn start`, the build process will automatically compile all of the source code in the `src` folder and put it into the `app` folder. This means that the `app` folder will contain the full, runnable application. This process ensures that the app is always up-to-date with the latest changes to the source code.

```
Rocket.Chat.Electron
├── build
│   └── icons
├── src
│   ├── app
│   │   ├── main
│   │   └── reducers
│   ├── deepLinks
│   ├── downloads
│   │   └── reducers
│   ├── i18n
│   ├── ipc
│   ├── jitsi
│   ├── navigation
│   ├── notifications
│   ├── public
│   │   └── images
│   │       ├── touch-bar
│   │       └── tray
│   │           ├── darwin
│   │           ├── linux
│   │           └── win32
│   ├── screenSharing
│   ├── servers
│   │   └── preload
│   ├── spellChecking
│   ├── store
│   ├── types
│   ├── ui
│   │   ├── assets
│   │   ├── components
│   │   │   ├── AboutDialog
│   │   │   ├── AddServerView
│   │   │   ├── Dialog
│   │   │   ├── DownloadsManagerView
│   │   │   ├── ScreenSharingDialog
│   │   │   ├── SelectClientCertificateDialog
│   │   │   ├── ServersView
│   │   │   ├── SettingsView
│   │   │   │   └── features
│   │   │   ├── Shell
│   │   │   ├── SideBar
│   │   │   ├── UpdateDialog
│   │   │   └── utils
│   │   ├── icons
│   │   ├── main
│   │   │   └── serverView
│   │   ├── preload
│   │   └── reducers
│   ├── updates
│   └── userPresence
└── workspaces
    └── desktop-release-action
        ├── dist
        └── src
```

After setting up your application environment, you can move on to  [developing-your-desktop-app.md](developing-your-desktop-app.md "mention"). Customize it to align with your specific requirements.
