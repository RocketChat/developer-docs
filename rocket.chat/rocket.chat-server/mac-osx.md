# macOS

You can set up and run a Rocket.Chat development environment on your macOS system.

* [Apple Silicon](mac-osx.md#apple-silicon)
* [Non-Apple Silicon Chips](mac-osx.md#non-apple-silicon-chips)

## Apple Silicon

{% hint style="info" %}
Note: If you face any issues, see the [Troubleshooting](mac-osx.md#troubleshooting) section below.
{% endhint %}

* Install [Homebrew](https://brew.sh/)
* Install the [Node Version Manager (nvm)](https://github.com/nvm-sh/nvm)
    ```shell
    brew install nvm
    ```
  * Important!  Make sure you are running nvm version >= 0.39.2
    ```shell
    nvm --version
    ```
* [Fork the Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat/fork) into your own GitHub account
* Clone your fork of the Rocket.Chat repository to your local dev box, navigate into the directory, and configure an additional remote so we can later fetch updates from the main Rocket.Chat repo

    ```shell
    git clone https://github.com/your-username/Rocket.Chat
    cd Rocket.Chat
    git remote add upstream https://github.com/RocketChat/Rocket.Chat.git
    ```
* Find which version of node your version of RocketChat needs.
    ```
    cat package.json | grep -A4 engines | grep node
    ```
* Install that version of node, _for example_:
    ```
    nvm install 14.19.3
    ```


* Install yarn - read yarn's official documentation on [how to install yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable).
* Install Meteor - read the official documentation on [how to install Meteor](https://docs.meteor.com/install.html).


* Initialize the `meteor` framework.  This will show the version of meteor requested by Rocket.Chat
  (incidentally, specified in `apps/meteor/.meteor/release`) and will initialize it as a side-effect.

    ```shell
    cd apps/meteor
    meteor --version
    cd ../..
    ```

* Install all needed packages and build the Rocket.Chat app

    ```shell
    yarn
    yarn build
    ```

* Start your development server

    There are two ways to start the server.  For systems with >= 16 GB of memory, use

    ```shell
    yarn dev
    ```

    For systems with less than 16 GB of memory, use

    ```shell
    yarn dsv
    ```

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on macOS](<../../.gitbook/assets/image (51) (2).png>)

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

![Rocket.Chat server successfully running on macOS](<../../.gitbook/assets/image (51) (2).png>)

## Troubleshooting

### 1. Failure linking "fibers" (Apple Silicon)

If `yarn` is failing on the link step for fibers with a log similar to:

```
➤ YN0007: │ fibers@npm:5.0.3 must be built because it never has been before or the last one failed
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
```

* Install `node-gyp` globally

    ```shell
    npm install node-gyp --global
    ```

* Rebuild fibers for the system architecture manually

    ```shell
    cd node_modules/fibers
    node-gyp rebuild --arch=arm64
    ```

* Copy binary to the correct location

    ```shell
    mkdir bin/darwin-arm64-83
    cp build/Release/fibers.node bin/darwin-arm64-83/fibers.node
    ```

* Copy the rebuilt module into meteor

    ```shell
    cd ../..
    rm -rf apps/meteor/node_modules/fibers/
    cp -r node_modules/fibers apps/meteor/node_modules/
    ```

* Follow the instructions below for fixing a Bcrypt problem, even though its error
  message has not yet appeared.


### 2. Bcrypt requires arm64 binary but has amd64 one instead (Apple Silicon)

The error specifically looks like the following:

```
(mach-o file, but is an incompatible architecture (have 'x86_64', need 'arm64e')), '/usr/local/lib/bcrypt_lib.node' (no such file), '/usr/lib/bcrypt_lib.node' (no such file)
```

* Move to the bcrypt directory and rebuild everything

    ```shell
    cd node_modules/bcrypt
    make
    ```

* Copy the rebuilt module into meteor

    ```shell
    cd ../..
    rm -rf apps/meteor/node_modules/bcrypt
    cp -r node_modules/bcrypt apps/meteor/node_modules/
    ```
