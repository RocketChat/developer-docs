# Windows 10

Windows Subsystem for Linux 2 ([WSL2](https://docs.microsoft.com/en-us/windows/wsl/wsl2-index)) is a complete architectural overhaul of Linux on Windows, installing an entire Linux kernel (built by Microsoft) alongside the classic Windows kernel. The Linux and Windows kernels can now share system resources, such as memory and CPU, at a previously impossible granularity. Setting up Rocket.Chat on Windows requires using the WSL2.

## Requirements

### Software Requirements

Before you build Rocket.Chat on Windows 10,

* Ensure you have **Windows 10, version 2004** or above.
* Install and configure **WSL 2** following [Microsoft documentation](https://docs.microsoft.com/en-us/windows/wsl/install-win10).  Select **Ubuntu 20.04 LTS** distribution as your choice of Linux.
* Download and install the latest [Linux Kernel Updates](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel).

### Machine Requirements

You will need a Windows machine with the following minimum requirement to develop Rocket.Chat,

* 12 GB of RAM (16+ GB highly recommended)
* Four or more cores on CPU (at least 3 GHz boosted, 4.2 GHz or higher recommended)
* 80 GB of available fast SSD storage (PCIe 4.0 NVMe SSD recommended)

Before setting up a development environment on Windows, here are some essential things to note:

* &#x20;There is no need to install Mongo, NodeJs, or NPM separately.
* Clone the Rocket.Chat repository under `~` (`/home/username`) directory. Otherwise, [MongoDB won't start](https://stackoverflow.com/a/39278452).
* Use a regular user account, not an administrator.
* During the build, you may notice _peer or transitive dependencies warnings_. They are typically safe to ignore unless you are coding the required features or modules.

## Setting up a Development Environment on Windows

* Open a **WSL 2 shell** and update the distro by running this command.

```
 sudo apt-get update && sudo apt-get dist-upgrade -y
```

* Install tools required

```
sudo apt-get install build-essential git curl python3-minimal pkg-config
```

* Install [Meteor](https://www.meteor.com/install).

```
curl https://install.meteor.com/ | sh
```

{% hint style="info" %}
Sometimes, you may need to install an older release of Meteor. Always check the `.meteor/release` file of the GitHub code repository.
{% endhint %}

* There is no need to install `node` or `npm`, as Meteor already includes them. Confirm by running this command:

```
meteor node -v
meteor npm -v
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* Install the [n node package manager](https://www.npmjs.com/package/n) or [nvm ](https://github.com/nvm-sh/nvm)to help you manage node versions on your machine. You can use it to switch to any specified node version.

```bash
npm install -g n
n 14.21.3
node -v
```

* Install the `yarn` package manager.&#x20;

```
npm install --global yarn
```

* Fork the Rocket.Chat repository on [GitHub](https://github.com/RocketChat/Rocket.Chat). Open the WSL 2 shell and navigate to `/home/yourusername`  directory.  Then, pull the code by running this command:

```
git clone https://github.com/yourforkedrepo.git
```

{% hint style="info" %}
To install Git on Linux, see the [official guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
{% endhint %}

* Navigate into the directory and install all the dependencies by running this command:

```
cd Rocket.Chat
yarn
```

* When completed, build and run the server by executing

```
yarn build
yarn dev
```

{% hint style="info" %}
The first build can take ten or more minutes, and you may see various warnings or minor errors. Subsequent dev builds will take lesser time.
{% endhint %}

* The server will start up on port `3000` and you will see the "Server Running"  screen

![](<../../../.gitbook/assets/image (23).png>)

A successful running server will open up port `3000` on your machine where you can access Rocket.Chat using any browser or the Rocket.Chat client app through `http://localhost:3000`

## Editing Rocket.Chat Files on Windows

On Windows 10, the recommended IDE to use is Visual Studio Code. Install [Visual Studio Code](https://code.visualstudio.com/download) from Windows and ensure you install the VS Code extension named [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl). Optionally, you can install the [Windows Terminal](https://www.microsoft.com/en-ca/p/windows-terminal-preview/9n0dx20hk701?rtc=1) extension.

To edit Rocket.Chat files,

* Open the cloned repository folder on your IDE.
* When you make changes to Rocket.Chat the server will automatically rebuild.
* Sometimes changes can shut down the server. If that happens, run `yarn dev` again.
