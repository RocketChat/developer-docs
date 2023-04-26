# Developing your Desktop App

## Development

### TypeScript

Following the recent changes in the codebase, developing desktop apps takes into consideration the use of TypeScript 4. This is to address issues regarding maintainability.

Be sure to check out the [TypeScript 4 release handbook](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-0.html) and be updated.

### The Build Pipeline

The build process is founded upon [rollup](https://rollupjs.org/) bundler which compiles and brings every piece together. There are three entry files for your code:

* `src/main.ts`, the script running at the main Electron process, orchestrating the whole application;
* `src/rootWindow.ts`, the script that renders the UI of the _root window_, the app's main window;
* and `src/preload.ts`, which runs in a privileged mode to connect the app and the webviews rendering Rocket.Chat's web client.

### Adding Node.js Modules

To extend the app's functionalities with modules, always remember to differentiate between modules needed as `dependencies` and `devDependencies` in `package.json.` Like any other package depending project, only modules listed in `dependencies` will be included in the final distributable app.

## Servers

### Default Servers

Default servers can be specified to automatically connect when the application runs. This can be done by creating a `servers.json` file in the project root directory. When specified, the server list sidebar automatically gets populated on running the app or when all servers are removed.

The file syntax is as follows:

{% code title="servers.json" %}
```json
{
  "Demo Rocket Chat": "https://demo.rocket.chat",
  "Open Rocket Chat": "https://open.rocket.chat",
  "Awesome Rocket Chat": "https://awesome.rocket.chat"
}
```
{% endcode %}

### Pre-Release Configuration

You can bundle a `servers.json` with the install package, the file should be located in the root of the project application (same level as the `package.json`).

If the file is found, the initial "**Connect to server**" screen will be skipped and it will attempt to connect to the first server defined in the array. When that is done, it will take the user straight to the login screen.

{% hint style="info" %}
Note that the `servers.json` will only be checked if no other servers have already been added, even if you uninstall the app without removing older preferences, it will not be triggered again.
{% endhint %}

### Post-Install Configuration

If you cannot (or don't want to) bundle the file inside the app, you can create a `servers.json` in the user preferences folder which will overwrite the packaged one. The file should be located in any of the directories listed below.

{% tabs %}
{% tab title="Windows" %}
* `~\Users\<username>\AppData\Roaming\Rocket.Chat\`
* `~\Program Files\Rocket.Chat\Resources\`
{% endtab %}

{% tab title="macOS" %}
* `~/Users/<username>/Library/Application Support/Rocket.Chat/`
* `~/Applications/Rocket.Chat.app/Contents/Resources/`
{% endtab %}

{% tab title="Linux" %}
* `/home/<username>/.config/Rocket.Chat/`
* `/opt/Rocket.Chat/resources/`
{% endtab %}
{% endtabs %}

## Testing

### **Unit tests**

We use [Jest](https://jestjs.io/) testing framework with the [Jest electron runner](https://github.com/facebook-atom/jest-electron-runner). It searches for all files in the `src/` directory that matches the glob pattern `*.(spec|test).{js,ts,tsx}` and performs tests on them.

Run this command to execute tests on your changes.

```bash
yarn test
```

## Making a Release

To package your app into an installer use command:

```bash
yarn release
```

This starts the packaging process for the operating system you are running this command on. When it is done, the output file is ready for distribution and can be found in the `dist/` directory.

All packaging actions are handled by [electron-builder](https://www.electron.build/). It has a lot of customization options not mentioned here.
