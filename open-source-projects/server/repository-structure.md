# Repository Structure

Gaining a deep understanding of our server repository's structure is a foundational requirement for developers. In this guide, you'll gain insight into the organized framework of the Rocket.Chat server repository, facilitating your navigation and understanding of its key components.

The Rocket.Chat Server embodies readability, maintainability, and real-time data handling. Its[ architectural design](../../getting-started/architecture-and-components.md) prioritizes modularity and clarity, reflected in the repository structure that segregates functions for diverse developer levels. This guide delves into this structure, exploring directories, functionalities, and organizational principles.

Rocket.Chat uses a [monorepo](https://github.com/RocketChat/fuselage/wiki#fuselage-monorepo) to house essential code and packages required by various Rocket.Chat projects like the [Apps Engine](https://github.com/RocketChat/Rocket.Chat.Apps-engine), [LiveChat](https://github.com/RocketChat/Rocket.Chat.Livechat), etc. This makes it easier to maintain and share the code, and it allows developers to work on different projects simultaneously.

Rocket.Chat uses the [Meteor framework](https://www.meteor.com/) and [React](https://reactjs.org/) to build its components. You should be familiar with the [**Meteor project structure**](https://guide.meteor.com/structure.html) **and** [**React project structure**](https://reactjs.org/docs/faq-structure.html) to understand the Rocket.Chat repository structure.&#x20;

{% hint style="info" %}
&#x20;In the near future, Rocket.Chat will be moving away from Meteor to a more manual structure, which will allow it to be more flexible and scalable.
{% endhint %}

### Directory Structure

```
Rocket.Chat
├── README.md
├── _templates/
├── apps/
│   └── meteor/
│       ├── app/            # Features of Rocket.Chat
│       ├── client/         # General frontend only related code 
│       ├── definition/
│       ├── ee/             # Enterprise related code
│       ├── imports/
│       ├── install.sh*
│       ├── lib/            # Helper functions, classes, and methods
│       ├── package.json
│       ├── packages/       # Meteor packages customized in use
│       ├── private/        # Private files and assets only available within the project
│       ├── public/         # Publicly available files served directly from the project root
│       ├── server/         # Server side only code
│       ├── tests/          # Tests
├── ee/
│   └── apps/
├── package.json
├── packages/               # Houses sharable code that can be used by different projects
│   ├── agenda/
│   ├── api-client/
│   ├── cas-validate/
│   ├── core-typings/       # Type definitions used for core Rocket.Chat
│   │   ├── src/
│   ├── eslint-config/      # Config files and rules for code and unit tests
│   │   ├── best-practices/
│   │   ├── errors/
│   │   ├── ...
│   │   └── variables/
│   ├── livechat/
│   ├── model-typings/
│   ├── models/
│   ├── rest-typings/        # Signatures of endpoints
│   ├── ui-client/
│   ├── ui-contexts/
│   └── ui-video-conf/
```

**`apps/meteor/app/`**

In this directory, you'll discover a range of features offered by Rocket.Chat. Each primary folder here contains a `client/` and `server/` subdirectory, housing feature-specific code for the feature respectively. Occasionally, a lib/ directory contains code usable by both the app's server and client .&#x20;

{% hint style="info" %}
To learn more, see the  [Meteor guide](https://guide.meteor.com/structure.html).
{% endhint %}

{% hint style="warning" %}
Rocket.Chat is incorporating new features that won't adhere to the legacy Meteor structure within the `apps/` directory. These new features will adopt a distinct structure, while the existing code structure will continue to be mantained.
{% endhint %}

**`apps/meteor/client/views/`**

When client-side users see a Rocket.Chat page, it's the result of multiple components working together. A good starting point for beginners to see how this works is the `apps/meteor/client/views/` directory, which contains all of the views for Rocket.Chat. The root view of Rocket.Chat, which is the first file that is executed when a user opens Rocket.Chat in their web browser, can be found in `apps/meteor/client/views/root/AppRoot.tsx`.

**`apps/meteor/client/lib/`**

It contains a collection of objects that are reused on all of the client sides. This is done to limit code duplication, encourage contributors to use the code that is already existing in the codebase, and avoid re-implementing logic or re-creating functions.

**`apps/meteor/packages/`**

This directory houses any meteor packages used in the project or customized for a specific purpose. Notable examples include the [meteor-accounts-linkedin](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/packages/accounts-linkedin) for Linkedin login service, [rocketchat-i18n](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/packages/rocketchat-i18n) for internationalization, etc.

**`apps/meteor/server/methods/`**

All meteor methods are located here.

**`apps/meteor/server/lib/`**

The `apps/meteor/server/lib/` directory holds versatile functions related to server-side code.

Now that you are familiar with the repository structure, you can confidently continue with your [server-environment-setup](server-environment-setup/ "mention").
