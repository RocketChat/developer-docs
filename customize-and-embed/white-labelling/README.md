# White Labelling

Rocket.Chat offers a wide range of customization options, including basic color switching and complete CSS control. More importantly, you can make customizations without changing the source code.

{% hint style="info" %}
To learn more, see [Basic White-Labeling](https://docs.rocket.chat/quick-start/basic-white-labeling) and [Advanced White-Labeling](broken-reference).
{% endhint %}

## Customizing Rocket.Chat from Code

Rocket.Chat is open source and flexible for customization and modifications.

{% hint style="warning" %}
Rather than making changes from the forked Rocket.Chat repository, developers are advised to focus on building the same codebase that can be customized for each user.&#x20;
{% endhint %}

If you are customizing Rocket.Chat's codebase, it is assumed that you are a developer. As a developer, your focus should be building the product, then packaging it in your desired format.

Fork the [Rocket.Chat GitHub repository](https://github.com/RocketChat/Rocket.Chat) and make necessary changes based on your requirements to the following:

* Adding new packages
* Building Custom UIs
* Extending logic, etc

{% hint style="info" %}
Due to the unique needs of each user, it is difficult to provide detailed information on the specific customizations that can be made with the Rocket.Chat codebase. The extent and nature of these customizations will depend on individual requirements and preferences.
{% endhint %}

### Deploying a Customized version of Rocket.Chat

Suppose you are planning to build a custom deployment option for Rocket.Chat, such as a Docker image or snap package, refer to the Rocket.Chat [Dockerfile](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.docker/Dockerfile) and [build script](https://github.com/RocketChat/Rocket.Chat/actions/workflows/build\_and\_test.yml). These files contain all the necessary information and tools to start your customization.

## Advanced White-Labeling of server

You can customize your workspace extensively, allowing you to adjust layouts and customize email templates according to your preferences.&#x20;

### Layout

Customize the look of your workspace with custom CSS and Javascript by following the guide below.

{% embed url="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/layout#custom-css" %}

### Email Templates

Customize emails sent from your workspace and email notifications following the guide below.

{% embed url="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/email" %}
