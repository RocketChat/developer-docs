# Windows 10

> For resolving known common problems, see the [troubleshoot](windows-10.md#troubleshooting) section at the end of this page.

Microsoft released Windows Subsystem for Linux 2 ([WSL2](https://docs.microsoft.com/en-us/windows/wsl/wsl2-index)) in June of 2020. Before this time, the development of large and complex NodeJS-based servers/full-stack applications such as Rocket.Chat on Windows was close to impossible.

WSL 2 is a complete architectural overhaul of Linux on Windows, installing a full genuine Linux kernel (built by Microsoft) alongside the classic Windows kernel. The Linux kernel and Windows kernel can now share system resources, such as memory and CPU, at a granularity not previously possible. It also includes major performance optimization on cross-subsystems file sharing, boot, and other developer-relevant areas.

You must be using **Windows 10, version 2004 or later** to take advantage of WSL2, and to set up Rocket.Chat development.

![](../../.gitbook/assets/msinfo.png)

## Requirements

### Software Requirements

The following are prerequisites for developing Rocket.Chat on Windows 10:

1. Make sure you have **Windows 10, version 2004** or later
2. Install and configure **WSL 2** by following [Microsoft documentation,](https://docs.microsoft.com/en-us/windows/wsl/install-win10) making sure to select **Ubuntu 20.04 LTS** distribution as your choice of Linux
3. Download and install the latest [Linux Kernel Updates](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel)

### Machine Requirements

Building Rocket.Chat code requires a minimum of 8 GB of RAM memory on the Linux subsystem. (If you are not doing any development, and just deploying a Rocket.Chat server - the RAM required can be as low as 1GB.) On version 2004, about 4 GB of RAM appears to be reserved for the Windows subsystem. You will need a Windows machine with the following minimum requirement to develop Rocket.Chat:

* 12 GB of RAM memory (16+ GB highly recommended)
* 4 or more cores on CPU (at least 3 GHz boosted, 4.2 GHz or higher recommended)
* 80 GB of available fast SSD storage ( PCIe 4.0 NVMe SSD recommended)

## Setting up a Development Environment

> **IMPORTANT**: Note that there is no need to install mongo, nodejs, or npm separately
>
> **IMPORTANT:** You should work (clone) with Rocket.Chat code under `~` (`/home/username`) dir, otherwise [MongoDB won't start](https://stackoverflow.com/a/39278452).
>
> **NOTE:** Development should be performed under a regular user account, not Administrator.
>
> **NOTE:** During build, you may notice _WARNING_ related to _peer dependencies_ or other transitive dependencies. They are typically safe to ignore unless you are coding the feature or modules that require them.

* Open a **WSL 2 shell** (not Powershell) and update the distro by running

```
 sudo apt-get update && sudo apt-get dist-upgrade -y
```

* Install tools required

```
sudo apt-get install build-essential git curl python3-minimal pkg-config
```

* Install meteor

```
curl https://install.meteor.com/ | sh
```

(Under some circumstances, you may need to install a specific (older) release of Meteor instead of the latest, always check the `.meteor/release` file of the Github code repository to determine if you need to do this before you install meteor)

There is no need to install `node` or `npm`, as meteor already includes them. Verify by executing

```
meteor node -v
meteor npm -v
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

* It is recommended to use the `yarn` package manager. Install it by running

```
npm install --global yarn
```

* Fork the Rocket.Chat code from [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) and make sure you are on the WSL 2 filesystem, `pwd` should return `/home/yourusername`. When done, pull the code by executing

```
git clone https://github.com/yourforkedrepo.git
```

* Now navigate into the directory and install all the dependencies by running the following code

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
Start building (the first build can _take 10 or more minutes_, and you may see various warnings or minor errors -- please be patient; subsequent dev builds after the first will be 5 minutes or less)
{% endhint %}

The server will start up on port `3000` and you will see the following screen

![](<../../.gitbook/assets/image (23).png>)

A successful running of the server will open up port `3000` on your machine where you can access Rocket.Chat using any browser or the Rocket.Chat client app through `http://localhost:3000`

Other references:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Meteor](https://www.meteor.com/install)

## Editing Rocket.Chat Files

On Windows 10, the best coding environment to use is Visual Studio Code. Install [Visual Studio Code](https://code.visualstudio.com/download) from Windows. Make sure you also install the VS Code extension named [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) Optionally install the [Windows Terminal](https://www.microsoft.com/en-ca/p/windows-terminal-preview/9n0dx20hk701?rtc=1) extension

Editing files is relatively simple. You can go to the cloned repository folder and edit or add files to Rocket.Chat. From a WSL shell, you can start Visual Studio for Code using the command `code .` .

![](../../.gitbook/assets/vscode.png)

When you make changes to Rocket.Chat the server will automatically rebuild.

Sometimes changes can shut down the server, if that happens just run `yarn dev` again.

## Troubleshooting
