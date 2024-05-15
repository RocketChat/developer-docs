# Contribute to Apps-Engine

Being open source, we always welcome contributors to help us develop the ultimate chat platform. Contribute to our open source Apps-Engine framework, increasing the world of possibilities of integrations around the Rocket.Chat ecosystem. You can check out our Apps-Engine repository here.

{% embed url="https://github.com/RocketChat/Rocket.Chat.Apps-engine" %}

An excellent place to start looking at is our open issues and determining if you can help us with them.

{% hint style="info" %}
When developing new functionalities, you need to integrate the local version of the Apps-Engine with your local version of Rocket.Chat.
{% endhint %}

## Get the Apps-Engine code

1. To start, clone the Apps-Engine repository and navigate into the directory by running the following commands:

```bash
git clone https://github.com/RocketChat/Rocket.Chat.Apps-engine.git
cd Rocket.Chat.Apps-engine
```

2. Next, install all the required packages and compile the changes since that is what Rocket.Chat itself will execute.

```bash
npm install
npm run compile
```

3. Setup your Rocket.Chat environment following the guide on [server-environment-setup](../../open-source-projects/server/server-environment-setup/ "mention")
4. After setting up, go to the directory and run the following command:

```bash
meteor npm install PATH_TO_APPS_ENGINE
```

Here `PATH_TO_APPS_ENGINE` is the path to the Apps-Engine repo you cloned earlier.

5. You can now start your Rocket.Chat with the `meteor` command, it will use your local Apps-Engine instead of the one on NPM.

{% hint style="info" %}
Whenever you make changes to the engine, run `npm run compile` again - meteor will take care of restarting the server due to the changes.
{% endhint %}

## Troubleshooting Apps-Engine development

* Sometimes, when you update the Apps-Engine code and compile it while Rocket.Chat is running; you run into errors similar to these:

```bash
Unable to resolve some modules:

  "@rocket.chat/apps-engine/definition/AppStatus" in
/Users/dev/rocket.chat/Rocket.Chat/app/apps/client/admin/helpers.js (web.browser)

If you notice problems related to these missing modules, consider running:

  meteor npm install --save @rocket.chat/apps-engine
```

Restart the meteor process, and it should be fixed.

* Sometimes using `meteor npm install PATH_TO_APPS_ENGINE` causes the following error:

```bash
npm ERR! code ENOENT
npm ERR! syscall rename
npm ERR! path PATH_TO_ROCKETCHAT/node_modules/.staging/@rocket.chat/apps-engine-c7135600/node_modules/@babel/code-frame
npm ERR! dest PATH_TO_ROCKETCHAT/node_modules/.staging/@babel/code-frame-f3697825
npm ERR! errno -2
npm ERR! enoent ENOENT: no such file or directory, rename 'PATH_TO_ROCKETCHAT/node_modules/.staging/@rocket.chat/apps-engine-c7135600/node_modules/@babel/code-frame' -> 'PATH_TO_ROCKETCHAT/node_modules/.staging/@babel/code-frame-f3697825'
npm ERR! enoent This is related to npm not being able to find a file.
npm ERR! enoent 
```

Here `PATH_TO_ROCKETCHAT` is the path to the main Rocket.Chat server repo in your system. To fix this, we reinstall the package once again and delete the previous package.

```bash
~/Rocket.Chat$ rm -rf node_modules/@rocket.chat/apps-engine
~/Rocket.Chat$ cd PATH_TO_APP_ENGINE
~/Rocket.Chat.Apps-engine$ npm install
~/Rocket.Chat.Apps-engine$ cd PATH_TO_ROCKETCHAT
~/Rocket.Chat$ meteor npm install ../Rocket.Chat.Apps-engine
```
