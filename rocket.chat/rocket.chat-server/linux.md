# Linux

You can run Rocket.Chat for development on a clean Linux machine or VM.

{% hint style="info" %}
**Note**:

* You are required to have a minimum of 8GB RAM to build when running a development environment. 1GB RAM on the other hand is enough for normal deployment.
* There is no need to have `nodejs` or `mongo` pre-installed. Start with a clean system.
* Setup should be done on a regular user account(not `root`). Running with `sudo` can mess up file permissions
{% endhint %}

You may notice build WARNINGs related to _peer dependencies_ or other transitive dependencies. They are typically safe to ignore unless you are coding the feature or modules that require them.

* Install essential tools required by running:

```bash
sudo apt install g++ build-essential git curl python2-minimal
```

If you are using other OS (like Ubuntu 20.04 etc) you may run into an error "python-minimal has no installation candidate") To resolve this check out this [thread on Stackoverflow](https://askubuntu.com/questions/422975/e-package-python-software-properties-has-no-installation-candidate).

* Install Meteor by executing:

```bash
curl https://install.meteor.com/ | sh
```

Meteor comes pre-installed with npm and node, verify by executing:

```bash
meteor node -v
meteor npm -v
```

* Install Yarn if you don't already have it on your system. Yarn is the recommended package manager

```bash
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* To easily manage the node versions on your machine, install the [n node package manager](https://www.npmjs.com/package/n) or [nvm ](https://github.com/nvm-sh/nvm)then install and switch to the desired node version to use. Example:

```bash
npm install -g n
n 14.19.3
node -v
```

* Fork and clone the Rocket.Chat repository [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```bash
git clone https://github.com/<your-username>/Rocket.Chat
cd Rocket.Chat
```

* Run the following commands to navigate to the `meteor` directory and download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file

```bash
cd apps/meteor
meteor --version
```

* Navigate back into the main project root directory and install packages by simply running

<pre class="language-bash"><code class="lang-bash"><strong>cd ../../
</strong><strong>yarn</strong></code></pre>

* Build and startup your development server by executing the commands below. Building for the first time will take a while and you may see some warnings or errors.

```bash
yarn build
yarn dev
```

When the server is ready, you will see a box with "Server Running" title:

![Rocket.Chat Development server running](<../../.gitbook/assets/Rocket.Chat Development server running>)

This means that a Rocket.Chat server is running from your computer. To access the server, navigate to

`http://localhost:3000`

The code is spread through the folders, `packages/` and `apps/meteor`, the latter contains the vast majority of the project's code.

See[ Repository Structure](../repository-structure.md) for more.

Other references:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Meteor](https://www.meteor.com/install)

### Editing Rocket.Chat Files

Editing files is relatively simple. After you run `git clone`, the files from the repository are saved on your computer. You can go to the cloned repository folder and edit or add files to Rocket.Chat. When you make changes to Rocket.Chat the server will automatically rebuild.

Sometimes changes can shut down the server, if that happens just restart the server again.

The Rocket.Chat code base is very large. You may need to increase this [system parameter ](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md)on your operating system for the files-change watcher to operate efficiently.

## See Also

* [Supporting SSL for Mobile Apps](../../mobile-app/mobile-app-environment-setup/supporting-ssl-for-development-on-rocket.chat.md)
* [Development Troubleshooting](../../contribute-to-rocket.chat/ways-to-contribute/developing/troubleshooting.md)
* [Deployment Methods](linux.md)
