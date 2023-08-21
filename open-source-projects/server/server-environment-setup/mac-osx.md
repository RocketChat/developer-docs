# Mac OSX

You can set up and configure a  Rocket.Chat development environment on your macOS system running on [**Apple Silicon**](mac-osx.md#apple-silicon) or systems with [**non-Apple Silicon chips**](mac-osx.md#setting-up-a-rocket.chat-development-environment-non-apple-silicon-chips)**.**

## Apple Silicon

**Preparation Steps**

* Install [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)
* Install [Meteor](https://docs.meteor.com/install.html)
* Install [Homebrew](https://brew.sh/)
* Install the [Node Version Manager (nvm)](https://github.com/nvm-sh/nvm) with this command:

```bash
brew install nvm
```

{% hint style="warning" %}
Confirm that your nvm version is 0.39.2 or higher by running the command `nvm --version` in your terminal.
{% endhint %}

**Setting up a Rocket.Chat Development Environment on MacOS Apple Silicon**

* Fork the [Rocket.Chat repository](https://github.com/RocketChat) on GitHub. Clone the forked repository to your local dev box using this command:

```
git clone https://github.com/<your-username>/Rocket.Chat.git
```

* Navigate into the project directory and configure an additional remote so we can later fetch updates from the main Rocket.Chat repo with these commands:

<pre class="language-shell"><code class="lang-shell"><strong>git clone https://github.com/your-username/Rocket.Chat
</strong>git remote add upstream https://github.com/RocketChat/Rocket.Chat.git
</code></pre>

* Confirm the Node.js version required by your RocketChat version by executing the following command:

```
cat package.json | grep -A4 engines | grep node
```

* Install the required version of NodeJS replacing `x.x.x` with the required NodeJs version number:

```
nvm install x.x.x
```

* Initialize the `meteor` framework. This will show the version of meteor requested by Rocket.Chat (located in `apps/meteor/.meteor/release`). It will also initialize the framework.

```shell
cd apps/meteor
meteor --version
cd ../..
```

* Install all needed packages and proceed to build the Rocket.Chat app with these commands:

```shell
yarn
yarn build
```

* Start your development server.&#x20;

For systems with 16 GB of memory or higher, use this command:

```shell
yarn dev
```

For systems with less than 16 GB of memory, use

```shell
yarn dsv
```

Once it is finished, the following output will be displayed on your terminal and the local server will be running on _`http://localhost:3000`._

<figure><img src="../../../.gitbook/assets/Rocket.Chat server running on macOS.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
If you encounter any issues, see [#troubleshooting](mac-osx.md#troubleshooting "mention").
{% endhint %}

## Setting up a Rocket.Chat Development Environment Non-Apple Silicon Chips

{% hint style="warning" %}
This setup instruction has been tested on MacBook Pro 2015, 8Gig Ram, 512Gb SSD,i5.
{% endhint %}

* Install Meteor by executing this command:

```
curl https://install.meteor.com/ | sh
```

* Meteor comes pre-installed with npm and node, confirm the versions by executing this command:

```
meteor node -v
meteor npm -v
```

* Install [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable) if it's not already on your system. It is the recommended package manager.

```
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* To easily manage the node versions on your machine, install the [n node package manager](https://www.npmjs.com/package/n) and switch to your desired NodeJs version.

```
npm install -g n
n x.x.x
node -v
```

{% hint style="warning" %}
Replace x.x.x with the NodeJs version number.&#x20;
{% endhint %}

* Fork the [Rocket.Chat repository](https://github.com/RocketChat) on GitHub. Clone the forked repository and navigate to the project directory using this command:

```
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file:

```
cd apps/meteor
meteor --version
```

* Navigate to the project root directory and  install all the needed packages by executing this command:

```bash
cd ../..
yarn
```

* Build and startup your development server by running this command:

```
yarn build
yarn dev
```

Once it is finished, the following output will be displayed on your terminal and the local server will be running on _`http://localhost:3000`._

<figure><img src="../../../.gitbook/assets/Rocket.Chat server running on macOS.png" alt=""><figcaption><p>Rocket.Chat server successfully running on macOS</p></figcaption></figure>

You can modify the code in your IDE and see the changes on the server instance. Now, you can start contributing to Rocket.Chat!

## Troubleshooting

<details>

<summary>Failure linking "fibers" (Apple Silicon)</summary>

If `yarn` is failing on the link step for fibers with a log similar to:

```
➤ YN0007: │ fibers@npm:5.0.3 must be built because it never has been before or the last one failed
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
➤ YN0009: │ fibers@npm:5.0.3 couldn't be built successfully (exit code 1, logs can be found here: /private/var/folders/…/build.log)
```

*   Install `node-gyp` globally

    ```shell
    npm install node-gyp --global
    ```
*   Rebuild fibers for the system architecture manually

    ```shell
    cd node_modules/fibers
    node-gyp rebuild --arch=arm64
    ```
*   Copy binary to the correct location

    ```shell
    mkdir bin/darwin-arm64-83
    cp build/Release/fibers.node bin/darwin-arm64-83/fibers.node
    ```
*   Copy the rebuilt module into meteor

    ```shell
    cd ../..
    rm -rf apps/meteor/node_modules/fibers/
    cp -r node_modules/fibers apps/meteor/node_modules/
    ```
* Follow the instructions below for fixing a Bcrypt problem, even though its error message has not yet appeared.

</details>

<details>

<summary>Bcrypt requires arm64 binary but has amd64 one instead (Apple Silicon)</summary>



The error specifically looks like the following:

```
(mach-o file, but is an incompatible architecture (have 'x86_64', need 'arm64e')), '/usr/local/lib/bcrypt_lib.node' (no such file), '/usr/lib/bcrypt_lib.node' (no such file)
```

*   Move to the bcrypt directory and rebuild everything

    ```shell
    cd node_modules/bcrypt
    make
    ```
*   Copy the rebuilt module into meteor

    ```shell
    cd ../..
    rm -rf apps/meteor/node_modules/bcrypt
    cp -r node_modules/bcrypt apps/meteor/node_modules/
    ```

</details>
