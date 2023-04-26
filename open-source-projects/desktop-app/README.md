# Desktop App

The Rocket.Chat multiplatform client desktop app is developed with Electron.

Setting up the development environment requires you to download and install multiple dependencies. You will need an active internet connection throughout the process.

## Requirements

You are required to have the following installed already on your machine before starting.

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [node-gyp](https://github.com/nodejs/node-gyp#installation)
* [Yarn](http://yarnpkg.com/) is recommended instead of npm.

## Get the Code

* Open up your terminal/command line and navigate into your working directory.
* Clone the source code from [our repository](https://github.com/RocketChat/Rocket.Chat.Electron) and run it by executing the following command on your terminal.

```
git clone https://github.com/RocketChat/Rocket.Chat.Electron.git
cd Rocket.Chat.Electron
yarn
yarn start
```

### Project Structure

The source is located in the `src` folder. Everything in this folder will be built automatically when running the app with `yarn start`.

The build process compiles all stuff from the `src` folder and puts it into the `app` folder, so after the build has finished, your `app` folder contains the full, runnable application.

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
