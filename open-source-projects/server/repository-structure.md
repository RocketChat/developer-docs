# Repository Structure

Understanding the structure of software repositories is essential for both seasoned developers and beginners alike. This guide will focus on the Rocket.Chat Server, a part of the Rocket.Chat Open Source Project suite. Its server-side functionality is a key aspect of the ecosystem, hence understanding the [Rocket.Chat repository](https://github.com/RocketChat/Rocket.Chat) structure is integral to understanding the platform as a whole.

Rocket.Chat Server is built with several principles in mind: readability, maintainability, and the ability to handle high-volume, real-time data. It adheres to a [clean architectural pattern](../../getting-started/architecture-and-components.md) which ensures that it remains modular and easy to comprehend. The server's repository structure is constructed to compartmentalize the software's various functionalities and processes, making it accessible to developers of different expertise levels. As we delve into this guide, we will examine the structure in greater depth, focusing on the different directories and their functionalities, as well as the underlying principles that guide the project's organization.

Rocket.Chat uses a [monorepo](https://github.com/RocketChat/fuselage/wiki#fuselage-monorepo) to house several pieces of required code and packages needed by various Rocket.Chat projects like the [Apps Engine](https://github.com/RocketChat/Rocket.Chat.Apps-engine), [LiveChat](https://github.com/RocketChat/Rocket.Chat.Livechat), etc.

This makes it easier to maintain and share the code without duplicating it.

{% hint style="info" %}
* Rocket.Chat uses [Meteor framework](https://www.meteor.com/) and [React ](https://reactjs.org/)to build components. You should be familiar with those and their project structure([**Meteor project structure**](https://guide.meteor.com/structure.html), [**React project structure**](https://reactjs.org/docs/faq-structure.html)) to better understand Rocket.Chat repository structure.
* In the nearest future, the Rocket.Chat codebase is diverting from Meteor to a more manual structure.
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

#### **`apps/meteor/app/`**

Here you will find the various features available in Rocket.Chat. Each main folder under this directory has a **`client/`** and a **`server/`** subdirectories that hold the client and server-side code for that feature, respectively.\
In some cases, you will find the **`lib/`** directory, which contains code that can be used by both the server and client part of the app.\
Learn more from the [Meteor guide](https://guide.meteor.com/structure.html).

{% hint style="success" %}
New features are being added to Rocket.Chat and will not follow this legacy meteor structure under the **`apps/`**folder. It will follow a different structure, but the code in the existing structure will still be maintained.
{% endhint %}

#### **`apps/meteor/client/views/`**

Where a combination of multiple components comes together in action to build a single Rocket.Chat page is seen by client-side users.

{% hint style="info" %}
* **`apps/meteor/client/views/`**is a very good starting point for beginners to see and trace code functionality
* The root view here can be seen in **`apps/meteor/client/views/root/AppRoot.tsx`** where execution in the front begins
{% endhint %}

#### **`apps/meteor/client/lib/`**

A collection of objects that are reused on all of the client sides.\
This is to:

* Limit code duplication
* Encourage contributors to use the code that is already existing in the codebase
* Avoid re-implementing logic or re-create functions

#### `apps/meteor/packages/`

Any meteor packages used within the project or customized for a specific purpose.\
Examples include the [meteor-accounts-linkedin](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/packages/accounts-linkedin) for Linkedin login service, [rocketchat-i18n](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/packages/rocketchat-i18n) for internationalization, etc

#### `apps/meteor/server/methods/`

Has meteor methods.

#### `apps/meteor/server/lib/`

Has general-purpose functions relating to server-side code.
