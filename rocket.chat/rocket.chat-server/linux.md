# Linux

You can run Rocket.Chat for development on a Linux machine or VM. The following instruction has been tested on a new Ubuntu 18.04 LTS installation. Try to find and use a _NEW Ubuntu server installation_ with no other un-necessary software installed, not a "Desktop" or "Client" installation.

_DO NOT_ use a system where you already have nodeJS installed to avoid problems.

During the build, memory usage will be nearly 8G, this is the minimum level of RAM recommended for development workstations. (If you are not doing any development, and just deploying a Rocket.Chat server - the RAM required can be as low as 1G.)

IMPORTANT: Note that there is no need to install mongo, nodejs, or npm on the base operating system. If you have any of these already installed; start over, or use another CLEAN system.

Development should be performed under a regular user account (not `root`) on Linux. There should be no need to run `sudo` at all. Running `sudo`, even once, during the installation -- may mess up file permissions in irreversible manner.

You may notice build WARNINGs related to _peer dependencies_ or other transitive dependencies. They are typically safe to ignore unless you are coding the feature or modules that require them.

1.  Install tools required

    `sudo apt install g++ build-essential git curl python2-minimal`\
    ``(If you are using other OS (like Ubuntu 20.04 etc) you may run into an error "python-minimal has no installation candidate") To resolve this check out this [thread on Stackoverflow](https://askubuntu.com/questions/422975/e-package-python-software-properties-has-no-installation-candidate).
2.  Install meteor

    `curl https://install.meteor.com/ | sh`
3.  Get rocket.chat code

    `git clone https://github.com/RocketChat/Rocket.Chat.git`

    (you may want to fork the code on Github first, and then clone your fork)
4. Change current working directory to the cloned repo location
5. Run `meteor --version` , this will download the necessary meteor version for Rocket.Chat, as configured in `.meteor/release` file.

    NOTE: If you are just starting out, you may want to switch to the latest [stable release's tag](https://github.com/RocketChat/Rocket.Chat/tags). Since the current branch is under development and getting actively contributed, running it on your localhost may produce errors. In order to checkout a specific tag of the repository: `git checkout tags/<tag-name> -b <branch-name>`

6.  Install modules

    `meteor npm install`
7.  Start building (the first build can _take 10 or more minutes_, and you may see various warnings or minor errors -- please be patient; subsequent dev builds after the first will be 5 minutes or less)

    `meteor`

When the server is ready, you will see a box with "Server Running" title:

![](<../../.gitbook/assets/image (5).png>)

This means that a Rocket.Chat server is running from your computer. To access the server, navigate to

`http://localhost:3000`

Other references:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Meteor](https://www.meteor.com/install)

### Editing Rocket.Chat Files

Editing files is relatively simple. After you run `git clone`, the files from the repository are saved on your computer. You can go to the cloned repository folder and edit or add files to Rocket.Chat. When you make changes to Rocket.Chat the server will automatically rebuild.

Sometimes changes can shut down the server, if that happens just run `meteor` or `meteor npm start` again.

The Rocket.Chat code base is very large. You may need to increase this [system parameter ](https://github.com/meteor/docs/blob/master/long-form/file-change-watcher-efficiency.md)on your operating system for the files-change watcher to operate efficiently.

## See Also

* [Supporting SSL for Mobile Apps](../../mobile-app/mobile-app-environment-setup/supporting-ssl-for-development-on-rocket.chat.md)
* [Development Troubleshooting](../contribute-to-rocket.chat/troubleshooting.md)
* [Deployment Methods](linux.md)
