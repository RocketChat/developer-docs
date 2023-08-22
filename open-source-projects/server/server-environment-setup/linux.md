# Linux

Setting up a Rocket.Chat development server on Linux involves several steps, including installing the necessary dependencies, configuring the server, and deploying Rocket.Chat. This guide will walk you through the process step by step.&#x20;

{% hint style="info" %}
The sample Linux distribution for this guide is Ubuntu. However, the steps are similar for other Linux distributions.
{% endhint %}

## Requirements

* At least 12GB RAM is required for building in a development environment. For deployment and other uses, 2GB RAM suffices.
* Use a standard user account (not root) for setup. Avoid using sudo to prevent potential file permission issues.

{% hint style="warning" %}
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

* Install **NodeJs 14.x (LTS)** either [manually](https://nodejs.org/dist/latest-v14.x/) or using a tool like [nvm](https://github.com/creationix/nvm) or [volta](https://volta.sh/).

{% hint style="warning" %}
Kindly check the [releases](https://github.com/RocketChat/Rocket.Chat/releases) to see the required NodeJS  version for Rocket.Chat.
{% endhint %}

* Install [Meteor](https://www.meteor.com/install) with this command:

```
curl https://install.meteor.com/ | sh
```

{% hint style="warning" %}
Occasionally, you might have to install a previous Meteor release. Ensure to verify the required Meteor version for Rocket.Chat from the  [`.meteor/release file`](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.meteor/release)`.`
{% endhint %}

Alternatively, install a specific Meteor version using this command replacing `x.x` with the version number:

```
curl https://install.meteor.com/?release=x.x | sh
```

* Install the [`yarn`](https://yarnpkg.com/getting-started/install) package manager with this command.

```
npm install --global yarn
```

* Fork the Rocket.Chat repository on [GitHub](https://github.com/RocketChat/Rocket.Chat) and clone it to your local system.

```
git clone https://github.com/<your-username>/Rocket.Chat.git
```

{% hint style="info" %}
To install Git on Linux, see the [official guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
{% endhint %}

* Navigate to the project directory and install all the dependencies by running these commands:

```
cd Rocket.Chat
yarn
```

* When completed, build and run the server by executing this command:

```
yarn dsv
```

{% hint style="info" %}
The first build can take ten or more minutes, and you may see various warnings or minor errors. Subsequent dev builds will take lesser time.
{% endhint %}

* The server will start up on port `3000` and you will see the "Server Running" screen:

![Rocket.Chat Development server running](<../../../.gitbook/assets/Rocket.Chat Development server running>)

A successful running server will open up port `3000` on your machine where you can access Rocket.Chat using any browser or the Rocket.Chat client app through `http://localhost:3000`

### Editing Rocket.Chat Files on Linux

For editing Rocket.Chat files,

1. Launch your IDE and navigate to the cloned repository folder.
2. Any modifications to Rocket.Chat trigger an automatic server rebuild.
3. Occasionally, changes might cause the server to shut down. In such cases, simply restart the server to continue.

{% hint style="info" %}
Given the extensive Rocket.Chat codebase, it's necessary to adjust the [system parameter](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md) on your OS to optimize the efficiency of the file-change watcher.
{% endhint %}

#### **References**

* [Development Environment Troubleshooting](../../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/troubleshooting.md)

Now that your development server is running, you're welcome to contribute to the Rocket.Chat server! See [participate-in-rocket.chat-development](../../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/ "mention") to learn more about Rocket.Chat contributions.
