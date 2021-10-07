# Desktop App Building From Source

**Prerequisites**:

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [node-gyp](https://github.com/nodejs/node-gyp#installation)
* [Yarn](http://yarnpkg.com/) is recommended instead of npm.

Now just clone and start the app:

```bash
git clone https://github.com/RocketChat/Rocket.Chat.Electron.git
cd Rocket.Chat.Electron
yarn
yarn start
```

#### Structure of the project

The source is located in the `src` folder. Everything in this folder will be built automatically when running the app with `yarn start`.

The build process compiles all stuff from the `src` folder and puts it into the `app` folder, so after the build has finished, your `app` folder contains the full, runnable application.

#### TypeScript

Following the \[ongoing changes in Rocket.Chat codebase\]\[\], the app was rewritten in TypeScript 4 to address issues regarding maintainability.

#### The build pipeline

The build process is founded upon \[rollup\]\[\] bundler. There are three entry files for your code:

* `src/main.ts`, the script running at the main Electron process, orchestrating the whole application;
* `src/rootWindow.ts`, the script that renders the UI of the _root window_, the app's main window;
* and `src/preload.ts`, which runs in a privileged mode to connect the app and the webviews rendering Rocket.Chat's web client.

**Adding Node.js modules**

Remember to respect the split between `dependencies` and `devDependencies` in `package.json` file. Only modules listed in `dependencies` will be included into distributable app.

#### Troubleshooting

**node-gyp**

Follow the installation instruction on \[node-gyp readme\]\[\].

**Ubuntu**

You will need to install the following packages:

```bash
build-essential
libevas-dev
libxss-dev
```

**Fedora**

You will need to install the following packages:

```bash
libX11
libXScrnSaver-devel
gcc-c++
```

**Windows 7**

On Windows 7 you may have to follow option 2 of the \[node-gyp install guide\] and install Visual Studio.

#### Testing

**Unit tests**

```bash
yarn test
```

We use \[Jest\]\[\] testing framework with the \[Jest electron runner\]\[\]. It searches for all files in `src` directory that match the glob pattern `*.(spec|test).{js,ts,tsx}`.

#### Making a release

To package your app into an installer use command:

```bash
yarn release
```

It will start the packaging process for the operating system you are running this command on. Ready for distribution file will be outputted to `dist` directory.

All packaging actions are handled by \[electron-builder\]\[\]. It has a lot of \[customization options\]\[\].

### Default servers

The `servers.json` file will define what servers the client will connect and will populate the server list in the sidebar. It contains a list of default servers which will be added the first time the user runs the app \(or when all servers are removed from the list\). The file syntax is as follows:

```javascript
{
  "Demo Rocket Chat": "https://demo.rocket.chat",
  "Open Rocket Chat": "https://open.rocket.chat"
}
```

#### Pre-Release Configuration

You can bundle a `servers.json` with the install package, the file should be located in the root of the project application \(same level as the `package.json`\). If the file is found, the initial "Connect to server" screen will be skipped and it will attempt to connect to the first server in the array that has been defined and drop the user right at the login screen. Note that the `servers.json` will only be checked if no other servers have already been added, even if you uninstall the app without removing older preferences, it will not be triggered again.

#### Post-Install Configuration

If you can't \(or don't want to\) bundle the file inside the app, you can create a `servers.json` in the user preferences folder which will overwrite the packaged one. The file should be located in the `%APPDATA%/Rocket.Chat/` folder or the installation folder in case of an installation for all users \(Windows only\).

For Windows, the full paths are:

* `~\Users\<username>\AppData\Roaming\Rocket.Chat\`
* `~\Program Files\Rocket.Chat\Resources\`

On macOS, the full paths are:

* `~/Users/<username>/Library/Application Support/Rocket.Chat/`
* `~/Applications/Rocket.Chat.app/Contents/Resources/`

On Linux, the full paths are:

* `/home/<username>/.config/Rocket.Chat/`
* `/opt/Rocket.Chat/resources/`

