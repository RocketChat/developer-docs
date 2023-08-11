# Developing your Desktop App

Following the recent changes in the codebase, developing desktop apps takes into consideration the use of TypeScript 4. This adoption is aimed at addressing maintainability concerns. Consult the [TypeScript 4 release handbook](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-0.html) to stay informed and updated..

### The Build Pipeline

The build process is founded upon [rollup](https://rollupjs.org/) bundler which compiles and brings every piece together. There are three entry files for your code:

The foundation of the build process relies on the [rollup](https://rollupjs.org/) bundler, responsible for compiling and integrating all components. Your codebase has three entry files:

* `src/main.ts`: The script running at the main Electron process, orchestrating the whole application.
* `src/rootWindow.ts`: The script that renders the UI of the _root window_ which serves as the app's main window;
* `src/preload.ts`:  The script runs in a privileged mode to connect the app and the webviews rendering Rocket.Chat's web client.

**Adding Node.js Modules**

When extending the app's functionalities with modules, it's crucial to distinguish between modules required as `dependencies` and those marked as `devDependencies` in the `package.json` file.  Similar to any other project relying on packages, only modules listed in `dependencies` will be included in the final distributable app.

When extending the app's functionalities with modules, it's crucial to distinguish between modules required as dependencies and those marked as devDependencies in the package.json file. Similar to any other project relying on packages, only modules specified under dependencies will be incorporated into the eventual distributable application.

### Servers

**Default Servers**

To establish automatic connections when the application launches, you can define default servers. This involves creating a `servers.json` file in the root directory of the project. This configuration ensures that the server list sidebar is automatically populated when the app launches or when all servers are deleted.

The `servers.json` file syntax is as follows:

{% code title="servers.json" %}
```json
{
  "Demo Rocket Chat": "https://demo.rocket.chat",
  "Open Rocket Chat": "https://open.rocket.chat",
  "Awesome Rocket Chat": "https://awesome.rocket.chat"
}
```
{% endcode %}

**Pre-Release Server Configuration**

You have the option to bundle a `servers.json` file with the installation package. This file should be located at the root level of the project application, in the same directory as the `package.json` file. When the file is located, the initial "**Connect to server**" screen won't appear. Instead, the app will try to connect to the first server listed in the array. Once connected, the user will be taken directly to the login screen.

{% hint style="info" %}
Please be aware that the `servers.json` file will only be checked if no other servers have been added previously. Even if you uninstall the app without removing previous preferences, this check will not be triggered again.
{% endhint %}

**Post-Install Server Configuration**

If you are unable or prefer not to include the file within the app bundle, an alternative approach is available. You can generate a servers.json file in the user preferences folder, which will override the packaged one. This file should be positioned in any of the directories outlined below depending on your operating system:

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

### Testing

**Unit tests**

We use [Jest](https://jestjs.io/) testing framework with the [Jest electron runner](https://github.com/facebook-atom/jest-electron-runner). It searches for all files in the `src/` directory that matches the glob pattern `*.(spec|test).{js,ts,tsx}` and performs tests on them.

Run this command to execute tests on your changes:

```bash
yarn test
```

**Making a Release**&#x20;

To bundle your application into an installer, utilize the following command:

```
yarn release
```

This command initiates the packaging procedure for the specific operating system you're currently using. Once completed, the resulting output file is prepared for distribution and can be located in the _dist/_ directory.

It's important to note that all packaging operations are managed by [electron-builder](https://www.electron.build/). This tool offers a multitude of customization possibilities, although not all are detailed here.

Now that you have successfully deployed and developed your Rocket.Chat desktop application, you can proceed to[ debug it for any errors or unexpected behaviors](../../desktop-app/debugging-your-desktop-app.md).
