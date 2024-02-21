# White Labelling

Rocket.Chat, a robust open-source communication platform, provides a comprehensive suite of customization options, including the ability to white-label your workspace. White-labeling allows you to tailor the platform's appearance and functionality to align with your brand identity and specific needs, with or without altering the source code. This feature enhances the user experience, promotes brand consistency, and provides a unique, personalized touch to your communication platform.

{% hint style="info" %}
To learn more, see [Basic White-Labeling](https://docs.rocket.chat/quick-start/basic-white-labeling) without altering the source code.
{% endhint %}

**Customizing Rocket.Chat from Code**: Rocket.Chat's open-source nature encourages customization and modification. However, instead of making changes from a forked Rocket.Chat repository, developers are advised to build on the existing codebase, which can then be customized according to each user's needs. This approach ensures that the core functionality remains intact while allowing individualized adjustments.

If you are customizing Rocket.Chat's codebase, it is assumed that you are a developer. As a developer, your focus should be building the product, then packaging it in your desired format.

Fork the [Rocket.Chat GitHub repository](https://github.com/RocketChat/Rocket.Chat) and make necessary changes based on your requirements to the following:

* Adding new packages
* Building Custom UIs
* Extending logic, etc

{% hint style="info" %}
Due to the unique needs of each user, it is difficult to provide detailed information on the specific customizations that can be made with the Rocket.Chat codebase. The extent and nature of these customizations will depend on individual requirements and preferences.
{% endhint %}

**Deploying a Customized version of Rocket.Chat**: The process of deploying a customized version of Rocket.Chat is straightforward. If you're planning to build a custom deployment option, such as a Docker image or snap package, you can refer to the Rocket.Chat [Dockerfile](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.docker/Dockerfile) and [build script](https://github.com/RocketChat/Rocket.Chat/actions/workflows/build\_and\_test.yml). These resources provide all the necessary information and tools to kickstart your customization journey.

**Advanced White-Labeling of server**: Advanced white-labeling options also extend to server customization. You can extensively customize your workspace, adjust layouts, and personalize email templates to suit your preferences. This includes the ability to modify the appearance of your workspace with custom CSS and Javascript, as well as customizing emails sent from your workspace.

**Layout:** Customize the look of your workspace with custom CSS and Javascript by following the guide below.

{% embed url="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/layout#custom-css" %}

**Email Templates**: Customize emails sent from your workspace and email notifications following the guide below.

{% embed url="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/email" %}

Rocket.Chat's white-labeling feature, combined with color [customization options](customizing-colors.md), provides a powerful toolset for creating a unique, branded communication platform. By adjusting the color variables, you can ensure that your Rocket.Chat workspace aligns perfectly with your brand identity, providing a consistent and engaging user experience.
