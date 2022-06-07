# Customizing Rocket.Chat from Code

Rocket.Chat is open source and flexible for customization and modifications.

{% hint style="warning" %}
We do not encourage developers to make changes from their fork but instead focus on building the same codebase that can be customized for every user.

So if you are customizing Rocket.Chat code base we are assuming you are a developer..
{% endhint %}

To customize Rocket.Chat from the code, a developer should be able to take a look at our codebase and see how to build and then package in their desired format

&#x20;This is as simple as forking the Rocket.Chat repository [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) then make the necessary changes as you require from

* Adding new packages
* Building Custom UIs
* Extending logic, etc

{% hint style="info" %}
We cannot extend further on any specific customization that can be made with the codebase since it is different for everybody.
{% endhint %}

## Deploying Customize version of Rocket.Chat

To build or create a custom deployment option of Rocket.Chat be it a Docker image or snap package, we advised you to take a look at our [Dockerfile ](customizing-rocket.chat-from-code.md#undefined)and [build script](customizing-rocket.chat-from-code.md#undefined) which contains everything you need to work with.
