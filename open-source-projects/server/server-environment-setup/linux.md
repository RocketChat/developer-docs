# Linux

You can run Rocket.Chat for development on a clean Linux machine or Virtual Machine.

## Requirements

* A minimum of 12GB RAM to build when running a development environment. For deployment and non-development purposes, 2GB RAM is enough.
* No need to have `nodejs` or `mongo` pre-installed. Start with a clean system.
* Setup using a regular user account(not root). Running with `sudo` can mess up file permissions.

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

* Install [Meteor](https://www.meteor.com/install).

```
curl https://install.meteor.com/ | sh
```

* There is no need to install `node` or `npm`, as Meteor already includes them. Confirm by running this command:

```
meteor node -v
meteor npm -v
```

* Install the `yarn` package manager.&#x20;

```bash
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* Install the [n node package manager](https://www.npmjs.com/package/n) or [nvm ](https://github.com/nvm-sh/nvm)to help you manage node versions on your machine. You can use it to switch to any specified node version.

```bash
npm install -g n
n 14.21.1
node -v
```

* Fork the [Rocket.Chat repository on GitHub](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory.

```bash
git clone https://github.com/<your-username>/Rocket.Chat
cd Rocket.Chat
```

* Navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file

```bash
cd apps/meteor
meteor --version
```

* Navigate back into the project root directory and install packages by simply running the following commands:

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

To edit Rocket.Chat files,

* Open the cloned repository folder on your IDE.
* When you make changes to Rocket.Chat the server will automatically rebuild.
* Sometimes changes can shut down the server. If that happens, restart the server again.

{% hint style="info" %}
The Rocket.Chat code base is vast. You may need to increase this [system parameter ](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md)on your operating system for the files-change watcher to operate efficiently.
{% endhint %}

## References

* [Supporting SSL for Mobile Apps](../../mobile-app/supporting-ssl-for-development-on-rocket.chat.md)
* [Development Troubleshooting](../../../contribute-to-rocket.chat/ways-to-contribute/developing/troubleshooting.md)
* [Deployment Methods](linux.md)
