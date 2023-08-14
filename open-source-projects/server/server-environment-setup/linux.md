# Linux

You can set up the Rocket.Chat development server on either a Linux device or a virtual machine with Linux installed.

## Requirements

* At least 12GB RAM is required for building in a development environment. For deployment and other uses, 2GB RAM suffices.
* There's no requirement to have pre-installed Nodejs or Mongo. Begin with a fresh system.
* Utilize a standard user account (not root) for setup. Avoid using sudo to prevent potential file permission issues.

{% hint style="info" %}
You may notice build WARNINGs related to _peer dependencies_ or other transitive dependencies. They are typically safe to ignore unless you are coding the required features or modules.
{% endhint %}

## Setting up a Development Environment in Linux

* Install essential tools required by running this command:

```bash
sudo apt install g++ build-essential git curl python2-minimal
```

<details>

<summary>If you run into the error "python-minimal has no installation candidate." To  resolve this:</summary>

* Install `software-properties-common`

```
sudo apt-get install software-properties-common
```

`software-properties-common` package is an alternate one for `python-software-properties`.

for <= 12.04

```
sudo apt-get install python-software-properties
```

for >= 12.10

```
sudo apt-get install software-properties-common
```

</details>

* Install [Meteor](https://www.meteor.com/install) with this command:

```
curl https://install.meteor.com/ | sh
```

* There is no need to install `node` or `npm`, as Meteor already includes them. Confirm by running this command:

```
meteor node -v
meteor npm -v
```

* Install the [n node package manager](https://www.npmjs.com/package/n) or [nvm ](https://github.com/nvm-sh/nvm)to help you manage node versions on your machine. You can use it to switch to the [required node version](https://github.com/RocketChat/Rocket.Chat/releases) for Rocket.Chat.

```bash
npm install -g n
n 14.21.3
node -v
```

* Install the `yarn` package manager.&#x20;

```bash
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* Install the [n node package manager](https://www.npmjs.com/package/n) or [nvm ](https://github.com/nvm-sh/nvm)to help you manage node versions on your machine. You can use it to switch to any specified node version. Here is an example of switching node versions with the [n node package manager](https://www.npmjs.com/package/n) :

```bash
npm install -g n
n 14.21.1
node -v
```

{% hint style="warning" %}
Check the [release notes](https://github.com/RocketChat/Rocket.Chat/releases) for the compatible Node.js version and install it accordingly.
{% endhint %}

* Fork the [Rocket.Chat GitHub repository GitHub](https://github.com/RocketChat/Rocket.Chat), clone it to your local system navigate into the directory.

```bash
git clone https://github.com/<your-username>/Rocket.Chat
cd Rocket.Chat
```

* Navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file with these commands:

```bash
cd apps/meteor
meteor --version
```

* Navigate back to the project root directory and install the required packages by running the following commands:

<pre class="language-bash"><code class="lang-bash">cd ../../
<strong>yarn
</strong></code></pre>

* Build and startup your development server by executing this command:

```bash
yarn dsv
```

{% hint style="info" %}
Building for the first time will take a while, and you may see some warnings or errors.
{% endhint %}

* When the server is ready, you will see the "Server Running" screen:

![Rocket.Chat Development server running](<../../../.gitbook/assets/Rocket.Chat Development server running>)

A successful running server will open up port `3000` on your machine where you can access Rocket.Chat using any browser or the Rocket.Chat client app through `http://localhost:3000`

### Editing Rocket.Chat Files on Linux

For editing Rocket.Chat files,

1. Launch your IDE and navigate to the cloned repository folder.
2. Any modifications to Rocket.Chat trigger an automatic server rebuild.
3. Occasionally, changes might cause the server to shut down. In such cases, simply restart the server to continue.

{% hint style="info" %}
Given the extensive Rocket.Chat codebase, it's neccessary to adjust the [system parameter](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md) on your OS to optimize the efficiency of the file-change watcher.
{% endhint %}

**References**

* [Development Environment Troubleshooting](../../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/troubleshooting.md)
