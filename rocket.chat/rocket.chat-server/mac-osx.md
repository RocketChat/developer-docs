# Mac OSX

\
You can set up and run a Rocket.Chat development environment on your Mac OSX.

* [Apple Silicon](https://developer.rocket.chat/rocket.chat/rocket.chat-server/mac-osx#apple-silicon)
* [Non-Apple Silicon Chips](mac-osx.md#non-apple-silicon-chips)

## Apple Silicon

{% hint style="info" %}
* Node.js only has prebuilt binaries for [Apple Silicon](https://www.macworld.com/article/334279/apple-silicon-macs-may-be-a-reboot-of-the-g4-cube-and-colorful-imac-g3.html) as from `node v16`
* Rocket.Chat currently uses at least `meteor 2.5.6` which has support for Apple silicon chips. If you are to run an environment with a lesser version, consider using[ the Rosetta terminal](https://support.apple.com/en-us/HT211861).
{% endhint %}

* Install node with [nvm](https://github.com/nvm-sh/nvm). This will fetch the latest version of node and npm, which may necessarily be the needed versions, but there is no problem
* Install meteor and yarn globally by running

```
npm install meteor -g 
npm install yarn -g
```

* Fork and clone the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory to install the needed toolset, as configured in `.meteor/release` file

```
cd apps/meteor
meteor --version
```

* Change the `PATH` of node and npm to point to `~/.meteor/packages/meteor-tools/2.5.6/mt-os.osx.arm64/dev_bundle/bin` This will set the global node now to be the arm compatible version needed
* Verify this by running

```
node -v              # v14.18.3
which node           # /Users/debdut/.meteor/packages/meteor-tool/2.5.6/mt-os.osx.arm64/dev_bundle/bin/node
which npm            #/Users/debdut/.meteor/packages/meteor-tool/2.5.6/mt-os.osx.arm64/dev_bundle/bin/npm
```

* Navigate back to the project root, delete the `yarn.lock` file and run the following command to install all dependencies

```
yarn
```

{% hint style="info" %}
If you are facing any errors with fibers failing, try this to resolve that

* **Linking node binary:** `ln -svf $(which node) $(dirname $(which node))/nodejs`
* **manual rebuild**:\
  `cd node_modules/fibers/` \
  `node-gyp rebuild --arch=arm64` \
  `mkdir bin/darwin-aarch64-83` \
  `cp build/Release/fibers.node $_`
  *   Then&#x20;

      `cp -r node_modules/fibers apps/meteor/node_modules/`
{% endhint %}

* Build and startup your development server by executing

```
yarn build
yarn dev
```

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on MacOSX](<../../.gitbook/assets/image (51) (2).png>)

## Non-Apple Silicon Chips

{% hint style="info" %}
This setup instruction has been tested on MacBook Pro 2015, 8Gig Ram, 512Gb SSD,i5
{% endhint %}

* Install Meteor by executing:

```
curl https://install.meteor.com/ | sh
```

Meteor comes pre-installed with npm and node, verify by executing:

```
meteor node -v
meteor npm -v
```

* Install Yarn if you don't already have it on your system. Yarn is the recommended package manager

```
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* To easily manage the node versions on your machine, install the [n node package manager](https://www.npmjs.com/package/n) and switch to the desired node version you want to use

```
npm install -g n
n 14.18.3
node -v
```

* Fork and clone the Rocket.Chat repository [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file

```
cd apps/meteor
meteor --version
```

* Back in the main directory, install all the packages by simply running

```
yarn
```

* Build and startup your development server by executing

```
yarn build
yarn dev
```

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on MacOSX](<../../.gitbook/assets/image (51) (2).png>)
