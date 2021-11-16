---
description: >-
  Contribute to our Open Source Apps Engine framework increasing the world of
  possibilities of integrations around the Rocket.Chat ecosystem
---

# Contributing to Apps Engine

Being Open Source, we always welcome contributors to help us out with the development of the our ultimate chat platform. You can checkout our [Apps Engine repository](https://github.com/RocketChat/Rocket.Chat.Apps-engine) to have a look at the code and understand the gist of what is currently going on there. An Awesome place to start is looking at our open issues and see if you can help out there! We're alwaus t

When developing new functionalities, you need to integrate the local version of the Apps-Engine with your local version of Rocket.Chat.

First of all, make sure you've installed all required packages and compiled the changes you've made to the Apps-Engine, since that is what Rocket.Chat will execute:

```
npm install
npm run compile
```

Now, you need to setup a local Rocket.Chat server, [so head to the project's README for instructions on getting started](https://github.com/RocketChat/Rocket.Chat#development) (if you haven't already). Make sure to actually clone the repo, since you will probably need to add some code to it in order to make your new functionality work.

After that, `cd` into Rocket.Chat folder and run:

```
meteor npm install PATH_TO_APPS_ENGINE
```

Where `PATH_TO_APPS_ENGINE` is the path to the Apps-Engine repo you've cloned.

That's it! Now when you start Rocket.Chat with the `meteor` command, it will use your local Apps-Engine instead of the one on NPM :)

Whenever you make changes to the engine, run `npm run compile` again - meteor will take care of restarting the server due to the changes.

### Troubleshooting

1. Sometimes, when you update the Apps-Engine code and compile it while Rocket.Chat is running, you might run on errors similar to these:

```
Unable to resolve some modules:

  "@rocket.chat/apps-engine/definition/AppStatus" in
/Users/dev/rocket.chat/Rocket.Chat/app/apps/client/admin/helpers.js (web.browser)

If you notice problems related to these missing modules, consider running:

  meteor npm install --save @rocket.chat/apps-engine
```

Simply restart the meteor process and it should be fixed.

1. Sometimes when using `meteor npm install PATH_TO_APPS_ENGINE` will cause the following error :-

```
npm ERR! code ENOENT
npm ERR! syscall rename
npm ERR! path PATH_TO_ROCKETCHAT/node_modules/.staging/@rocket.chat/apps-engine-c7135600/node_modules/@babel/code-frame
npm ERR! dest PATH_TO_ROCKETCHAT/node_modules/.staging/@babel/code-frame-f3697825
npm ERR! errno -2
npm ERR! enoent ENOENT: no such file or directory, rename 'PATH_TO_ROCKETCHAT/node_modules/.staging/@rocket.chat/apps-engine-c7135600/node_modules/@babel/code-frame' -> 'PATH_TO_ROCKETCHAT/node_modules/.staging/@babel/code-frame-f3697825'
npm ERR! enoent This is related to npm not being able to find a file.
npm ERR! enoent 
```

Here `PATH_TO_ROCKETCHAT` is the path to the main rocketchat server repo in your system To correct this we reinstall the package once again deleting the previous package

```
~/Rocket.Chat$ rm -rf node_modules/@rocket.chat/apps-engine
~/Rocket.Chat$ cd PATH_TO_APP_ENGINE
~/Rocket.Chat.Apps-engine$ npm install
~/Rocket.Chat.Apps-engine$ cd PATH_TO_ROCKETCHAT
~/Rocket.Chat$ meteor npm install ../Rocket.Chat.Apps-engine
```
