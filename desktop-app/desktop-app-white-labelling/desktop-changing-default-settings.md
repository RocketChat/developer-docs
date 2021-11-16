---
description: >-
  We assume that you have already followed the past topic that explains how to
  run the code on your machine and that you are familiar with the development
  stack (git/node/javascript/electron).
---

# Desktop Changing Default Settings

## Introduction

In changing the Desktop App default settings, we assume you have followed the guide on [desktop-app-environment-setup.md](../desktop-app-environment-setup.md "mention") done and that you are familiar with the development stack (**git**/**node**/**javascript**/**electron**).

## Assets&#x20;

Usually, the first thing you want to change is the icons. There are few folders that you need to take note of. From your root project directory, assets can be changed or customized in the following directories.

```
./src/ui/icons/
./src/ui/assets/
```

Pay attention these files are React components and you can change them correctly. When the changes are done, generate your new files by running...

```bash
yarn build-assets
```

## About

To change the about screen, head on to `./src/ui/components/AboutDialog/index.tsx` where you can change the copyright. If you've changed the logo already, it will automatically reflect on this page.

```bash
const copyright = `© 2016-${new Date().getFullYear()}, Rocket.Chat`;
```

## Building and Packaging

We use [electron-builder](https://www.electron.build) to "compile" and produce the executable files, just check the file `electron-builder.json`

Here you probably want to change all references to the term `rocket.chat/rocket/chat.rocket/rocketchat` according to what each setting means

The electron-builder has a webpage explaining what each attribute means, and probably there they cover other uses that we don't. [https://www.electron.build/configuration/configuration](https://www.electron.build/configuration/configuration)

You probably should look at this section if you want to maintain the automatic update: [https://www.electron.build/configuration/publish](https://www.electron.build/configuration/publish)

After that you just need to run the following commands:

```bash
yarn build
yarn release
```

For more information or to see how we configure the CI/CD, please check out [https://github.com/RocketChat/Rocket.Chat.Electron](https://github.com/RocketChat/Rocket.Chat.Electron)
