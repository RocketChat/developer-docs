# Windows 10

Setting up Rocket.Chat on Windows requires using the WSL2. Windows Subsystem for Linux 2 ([WSL2](https://docs.microsoft.com/en-us/windows/wsl/wsl2-index)) is a complete architectural overhaul of Linux on Windows, installing an entire Linux kernel (built by Microsoft) alongside the classic Windows kernel. The Linux and Windows kernels can now share system resources, such as memory and CPU, at a previously impossible granularity.

## Preparation Steps

**Software Requirements**

* **Windows 10, version 2004** or above.
* Install and configure **WSL 2** following [Microsoft documentation](https://docs.microsoft.com/en-us/windows/wsl/install-win10). The default Linux distribution to be installed is Ubuntu.
* Download and install the latest [Linux Kernel Updates](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel).

**Machine Requirements**

To set up Rocket.Chat development environment, you'll require a Windows machine that meets the following minimum specifications:

* 12 GB of RAM (16+ GB highly recommended)
* Four or more cores on CPU (at least 3 GHz boosted, 4.2 GHz or higher recommended)
* 80 GB of available fast SSD storage (PCIe 4.0 NVMe SSD recommended)

Before establishing a Rocket.Chat development environment on Windows, consider these key points:

* Clone the Rocket.Chat repository under `~` (`/home/username`) directory. Otherwise, [MongoDB won't start](https://stackoverflow.com/a/39278452).

{% hint style="warning" %}
During the build, you may notice _peer or transitive dependencies warnings_. They are typically safe to ignore unless you are coding the required features or modules.
{% endhint %}

## Setting up a Rocket.Chat Development Environment on Windows

* Open the Ubuntu **WSL 2 shell** and update the distro by running this command.

```
 sudo apt-get update && sudo apt-get dist-upgrade -y
```

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

Alternatively, Install a specific Meteor version using this command replacing `x.x` with the version number:

```
curl https://install.meteor.com/?release=x.x | sh
```

* Install the [`yarn`](https://yarnpkg.com/getting-started/install) package manager with this command.

```
npm install --global yarn
```

* Fork the Rocket.Chat repository on [GitHub](https://github.com/RocketChat/Rocket.Chat). Open the WSL 2 shell and navigate to `/home/yourusername` directory. Then, pull the code by running this command:

```
git clone https://github.com/<your-username>/Rocket.Chat.git
```

{% hint style="info" %}
To install Git on Linux, see the [official guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
{% endhint %}

* Navigate into the directory and install all the dependencies by running these commands:

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

* The server will start up on port `3000` and you will see the "Server Running" screen

![](<../../../.gitbook/assets/image (23).png>)

A successful running server will open up port `3000` on your machine where you can access Rocket.Chat using any browser or the Rocket.Chat client app through `http://localhost:3000`

## Editing Rocket.Chat Files on Windows

On Windows 10, the recommended IDE to use is Visual Studio Code. Install [Visual Studio Code](https://code.visualstudio.com/download) from Windows and ensure you install the VS Code extension named [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl). Optionally, you can install the [Windows Terminal](https://www.microsoft.com/en-ca/p/windows-terminal-preview/9n0dx20hk701?rtc=1) extension.

To edit Rocket.Chat files,

* Open the cloned repository folder on your IDE.
* When you make changes to Rocket.Chat the server will automatically rebuild.
* Sometimes changes can shut down the server. If that happens, run `yarn dsv` again.

#### **References**

* [Development Environment Troubleshooting](../../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/troubleshooting.md)

Now that your development server is running, you're welcome to contribute to the Rocket.Chat server! See [participate-in-rocket.chat-development](../../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/ "mention") to learn more about Rocket.Chat contributions.
