---
description: >-
  We assume that you have already followed the past topic that explains how to
  run the code on your machine and that you are familiar with the development
  stack (git/node/javascript/electron).
---

# Changing default settings

{% page-ref page="../desktop-app-building-from-source.md" %}

## Assets 

Usually the first thing you want change are the icons. There are few folders that you need to change

```
$ ui/icons
$ ui/assets 
```

Pay attention these files are react components and you can change them correctly. After that we can generate our new files with:

```bash
yarn build-assets

```

## About

The next change is the about screen. Change the copyright, the logo has probably already been changed in the previous step.

```bash
./src/ui/components/AboutDialog/index.tsx


const copyright = `© 2016-${new Date().getFullYear()}, Rocket.Chat`;


```

## Building and Packaging

We use electron-builder to "compile" and produce the executable files, just check the file `electron-builder.json`

Here you probably want to change all references to the term `rocket.chat/rocket/chat.rocket/rocketchat` according to what each setting means

The electron-builder has a webpage explaining what each attribute means, and probably there they cover other uses that we don't. [https://www.electron.build/configuration/configuration](https://www.electron.build/configuration/configuration)

You probably should look at this section if you want to maintain the automatic update: [https://www.electron.build/configuration/publish](https://www.electron.build/configuration/publish)

After that you just need to run the following commands:

```bash
yarn build
yarn release
```

For more information or to see how we configure the CI/CD, please check out [https://github.com/RocketChat/Rocket.Chat.Electron](https://github.com/RocketChat/Rocket.Chat.Electron)

