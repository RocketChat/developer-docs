# Gitpod

The quickest way to set up a Rocket.Chat development environment is Gitpod. Gitpod runs a shared environment for developers working on open-source projects. Gitpod runs a shared environment for SaaS developers working on open-source projects. It hosts the entire development environment, and you can contribute to Rocket.Chat whenever you have access to a browser.

## Setting up a Development Environment in GitPod

* Go to [Gitpod](https://www.gitpod.io/#get-started).
* Enter the [Rocket.Chat GitHub project URL](https://github.com/RocketChat/Rocket.Chat) or the link to your forked repo of Rocket.Chat.
* Start your workspace and link it to your GitHub account if necessary. A workspace is created and loaded with a familiar Visual Studio Code environment.
* Start a terminal in your workspace and install Meteor.

{% hint style="info" %}
See the[ Rocket.Chat GitHub repository](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.meteor/release) to confirm the required Metoer version for Rocket.Chat before installing.
{% endhint %}

Run the following command, passing in the release you want.

```
curl https://install.meteor.com/?release=2.2 | sh
```

You can also simplify this process by running the following command:

```
curl https://install.meteor.com/?release=$(
    curl -so- https://raw.githubusercontent.com/RocketChat/Rocket.Chat/develop/apps/meteor/.meteor/release | cut -d@ -f2
) | sh
```

{% hint style="info" %}
There will be warning messages, and you do not need `sudo` (root access) on Gitpod.
{% endhint %}

* Add the newly installed meteor to your path by running this command:

```
export PATH=$PATH:/home/gitpod/.meteor
```

* Install the `node` dependencies.

```
yarn # installs the dependencies for all projects
```

* Set your `ROOT_URL.` Rocket.Chat server may misbehave without it.

```
export ROOT_URL=$(gp url 3000)
```

* Finally, build and start the Rocket.Chat server.

```
yarn build
yarn dev # it will build the sub projects and then run meteor project
```

The code is spread through the folders, `packages/` and `apps/meteor`. After a few minutes, your development environment is up and running.

![](../../.gitbook/assets/gitpodrunning.png)

Once the server starts, you will see a popup window indicating that your server is running on port 3000. Click the **Open Browser** button to view and interact with your Rocket.Chat server instance.

![](../../.gitbook/assets/gitpodfinal.png)

You can modify the code in Visual Studio Code and see the changes immediately on the server instance. Now, you can start contributing to Rocket.Chat!
