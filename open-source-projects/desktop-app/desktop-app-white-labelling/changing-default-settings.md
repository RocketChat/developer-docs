# Desktop Changing Default Settings

After successfully setting up your [..](../ "mention"), you have the option to change the app's default settings. In this guide, you'll learn how to customize various settings in the ROcket.Chat Desktop app.

{% hint style="info" %}
You are required to have basic knowledge of Git, Node, Javascript, and Electron.
{% endhint %}

### Assets

Commonly, the primary adjustment is altering icons. Some specific folders in your root project directory where assets can be customized include:

```
./src/ui/icons/
./src/ui/assets/
```

Take extra caution as these files are React components, ensure to modify them correctly. When the changes are done, generate your new files by running this command:

```bash
yarn build-assets
```

### Tray Icon

If you want to customize the TrayIcon, there are two ways:

* Open `public/images/tray` there you can check all current icons used by the application. You can change files if you want.
* Open and change `ui/icon/AppIcon.tsx` this is the icon base used to automatically generate all the icons, if you are used with `tsx/jsx` probably this is the easiest way to go.

For customizing the TrayIcon, you have two options:

1. Navigate to `public/images/tray` to review and potentially modify the icons used by the application. You can replace files as desired.
2. Alternatively, open and modify `ui/icon/AppIcon.tsx`file. It is the icon base used to automatically generate all the icons. If you're familiar with tsx/jsx, this might be the more straightforward approach to take. After making the changes, run this command:

```
yarn build-assets
```

### About

To change the About screen, navigate to `./src/ui/components/AboutDialog/index.tsx` where you can change the copyright. If you've changed the logo already, it will automatically reflect on this page.

```bash
const copyright = `© 2016-${new Date().getFullYear()}, Rocket.Chat`;
```

### Building and Packaging

We use [electron-builder](https://www.electron.build/) to "compile" and produce the executable files. To make any updates, check the file `electron-builder.json`. Update all references to the term `rocket.chat/rocket/chat.rocket/rocketchat` based on the context of each setting.

{% hint style="info" %}
See the[ electron-builder configuration](https://www.electron.build/configuration/configuration) guide for more details.

To maintain automatic updates, see the [electron-builder publish guide](https://www.electron.build/configuration/publish).
{% endhint %}

After making any  change in the configuration, build a new release by running these commands:

```bash
yarn build
yarn release
```

{% hint style="info" %}
See the [GitHub repository](https://github.com/RocketChat/Rocket.Chat.Electron) for more information on configuring CI/CD.
{% endhint %}
