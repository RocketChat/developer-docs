# Gitpod

If you are contributing to Rocket.Chat and will likely be working less than 50 hours a month on it, the quickest way to get started is via Gitpod.

## Rocket.Chat Everywhere Development Environment on Gitpod

Gitpod runs a shared environment SaaS for developers working on open source projects. Please be respectful of other developers' needs and support Gitpod on their commercial side if you are able to.

Gitpod hosts the entire development environment and you will be able to contribute to Rocket.Chat wherever and whenever you have access to a browser; even from Internet Cafes and Chromebooks.

## Steps for Gitpod Development

* Go to [https://gitpod.io](https://www.gitpod.io/#get-started) and enter the Rocket.Chat Github project URL [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) or supply the link to your forked repo of Rocket.Chat

![](../../.gitbook/assets/gitpodstart.png)

*   Start your workspace and link it to your GitHub account if necessary.

    A workspace will be created and loaded with a familiar Visual Studio Code environment
*   Next, start a terminal in your workspace and install [meteor](https://www.meteor.com).&#x20;

    Make sure you install the correct version of meteor. As of the time of this writing Rocket.Chat uses `meteor@2.2`.&#x20;

    To know which version you need, consult [this](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.meteor/release) file (tracking the current development branch, i.e. the most up to date).
* Then run the following command passing in the release you want

```
curl https://install.meteor.com/?release=2.2 | sh
```

You can also make this process simpler by running the following code snippet on your terminal.

```
curl https://install.meteor.com/?release=$(
    curl -so- https://raw.githubusercontent.com/RocketChat/Rocket.Chat/develop/apps/meteor/.meteor/release | cut -d@ -f2
) | sh
```

{% hint style="info" %}
There will be warning messages, you do not need `sudo` (root access) on Gitpod.
{% endhint %}

* Next, add the newly installed meteor to your path by running

```
export PATH=$PATH:/home/gitpod/.meteor
```

* Finally, install the `node` dependencies and start your server by running the following respectively.

```
yarn # installs the dependencies for all projects
```

* Now set your `ROOT_URL`, without it Rocket.Chat server might misbahave.

```
export ROOT_URL=$(gp url 3000)
```

* Finally, build and start the Rocket.Chat server.

```
yarn build
yarn dev # it will build the sub projects and then run meteor project
```

The code is spread through the folders, packages/ and apps/meteor, the latter contains the vast majority of the project's code.

After a few minutes, your development environment should be up and running.

![](../../.gitbook/assets/gitpodrunning.png)

Once the server starts, you will see a popup window indicating that your server is running on port 3000. Click the **Open Browser** button to view and interact with your Rocket.Chat server instance.

![](../../.gitbook/assets/gitpodfinal.png)

You can modify the code in Visual Studio Code and see the changes immediately on the server instance thanks to hot code reload.

Start contributing to Rocket.Chat!
