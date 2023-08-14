# Gitpod

The quickest way to set up a Rocket.Chat development environment is by using Gitpod. Gitpod offers a shared workspace for open-source project developers, including those working on SaaS projects like Rocket.Chat. It provides a hosted development environment accessible through a web browser, allowing you to contribute to Rocket.Chat conveniently.

## Set up a Rocket.Chat Development Environment in GitPod

To set up a Rocket.Chat enviroment on Gitpod,

* Go to [Gitpod](https://www.gitpod.io/#get-started).
* Create a **New Workspace**. Enter the [Rocket.Chat GitHub project URL](https://github.com/RocketChat/Rocket.Chat) or the link to your forked repo of Rocket.Chat.
* Initiate your workspace and, if needed, connect it to your GitHub account. This will set up a workspace with a familiar Visual Studio Code environment.
* Next, launch a terminal within your workspace and proceed to install Meteor with this command,  passing the required Metoer release:

```
curl https://install.meteor.com/?release=2.12 | sh
```

{% hint style="warning" %}
See the[ Rocket.Chat GitHub repository](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.meteor/release) to confirm the required Metoer version for Rocket.Chat before installing.
{% endhint %}

Alternatively, you can streamline the process by running this command:

```
curl https://install.meteor.com/?release=$(
    curl -so- https://raw.githubusercontent.com/RocketChat/Rocket.Chat/develop/apps/meteor/.meteor/release | cut -d@ -f2
) | sh
```

{% hint style="warning" %}
Expect warning messages during this process, and keep in mind that sudo (root access) is not necessary on Gitpod.
{% endhint %}

* Add the newly installed meteor to your path by running this command:

```
export PATH=$PATH:/home/gitpod/.meteor
```

* Install the `node` dependencies with this command:

```
yarn
```

{% hint style="danger" %}
You might encounter an error if your Node version doesn't meet Rocket.Chat's requirements. Check the [release notes](https://github.com/RocketChat/Rocket.Chat/releases) for the compatible Node.js version and install it accordingly.
{% endhint %}

* Set your `ROOT_URL.`  Your Rocket.Chat server may misbehave without it.

```
export ROOT_URL=$(gp url 3000)
```

* Finally, build and start the Rocket.Chat server.

```
yarn build
yarn dev # it will build the sub projects and then run meteor project
```

The code is spread through the folders, `packages/` and `apps/meteor`. After a few minutes, your development environment is up and running.

![](../../../.gitbook/assets/gitpodrunning.png)

Once the server starts a popup window will appear, confirming that your server is active on port _3000_. Click the "**Open Browser**" button to access and engage with your Rocket.Chat server instance.

![](../../../.gitbook/assets/gitpodfinal.png)

You can modify the code in Visual Studio Code and see the changes immediately on the server instance. Now, you can start contributing to Rocket.Chat!
