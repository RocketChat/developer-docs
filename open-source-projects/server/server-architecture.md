# Server Architecture

Explore the Rocket.Chat Server Architecture Guide—an illuminating dive into how our platform is structured. Discover scalable designs, component interactions, and more. Whether you're a developer or a curious user, this guide provides a clear and insightful journey into the architecture shaping the server's robust and versatile communication platform.

{% hint style="info" %}
See [architecture-and-components.md](../../getting-started/architecture-and-components.md "mention")for a holistic view of Rocket.Chat's architecture and components.
{% endhint %}

**Core Server**

This component contains packages essential for user authentication, messaging, and other core functionalities of the Rocket.Chat server.

**Database**

Rocket.Chat uses MongoDB to store its data, such as chat messages, user information, and system configurations.

**File Storage**

Additionally, the server employs a file storage system for storing assets, user files, images, and various media files.

## Services

The Rocket.Chat server architecture consists of internal and external services. Internal services operate within the meteor instance, closely integrated with the main process. On the other hand, external services can operate independently in separate processes.

### External Services

Some external services in ROcket.Chat includes the following:

* **Authorization**: The authorization service manages user authorization and permissions, ensuring users have the proper access rights to various functionalities. It can be horizontally scaled and is stateless.
* **Account**: It handles user account management, including creating, updating, and deleting. It facilitates user authentication methods like login and logout. This service is stateless and can be horizontally scaled.
* **Presence**: It handles [user presence management](https://docs.rocket.chat/use-rocket.chat/user-guides/notifications#user-presence), tracking, and updating the online status of the user. It can be horizontally scaled and is stateless.
* **StreamHub**: This service captures database changes and broadcasts real-time data to other services. It's currently a single-instance service without support for horizontal scaling.
* **DDPStreamer**: This service oversees DDP (Distributed Data Protocol) connections, managing client-server interactions, subscriptions, and data transmission to clients. It can be horizontally scaled.
* **AppsEngine**: This service handles [Rocket.Chat apps,](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides) managing their installation, updates, execution, and removal. Although it's designed for horizontal scaling, please note that this service is currently in the development phase.

### Internal Services

* **Banner**: This service oversees banners, including their creation, updates, and deletion.
* **LDAP**: This service manages [LDAP (Lightweight Directory Access Protocol)](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/ldap) integration, establishing connections to LDAP servers and overseeing user synchronization.
* **NPS**: This service collaborates with the Banner service to manage Net Promoter Score (NPS) surveys. It generates banners for specific users and manages survey responses.
* **Room**: Manages chat rooms, including creation, updating, and deletion.
* **OmniChannel**: It's responsible for managing various omnichannel tasks.
* **Omnichannel Voip**: It handles VoIP (Voice over Internet Protocol) calls within the omnichannel system.
* **Team**: It manages teams within Rocket.Chat, including creation, updating, and deletion.
* **UiKitCoreApp**: This service handles UI Kit actions and events, utilizing the AppsEngine service for app-related tasks and events, along with Meteor Legacy for core actions.
* **Push**: This service is responsible for managing [push notifications](https://docs.rocket.chat/use-rocket.chat/rocket.chat-mobile/push-notifications), and sending them to mobile applications.
* **Upload**: This service oversees file uploads, including uploading files to the file system and handling file management.
* **Messaging**: This service is accountable for managing messages within Rocket.Chat.
* **Settings**: This service is in charge of managing system settings, involving tasks like creating, updating, and deleting settings.

In essence, the Rocket.Chat Server Architecture represents a sophisticated blend of components, seamlessly uniting to create a robust communication platform. From user authorization to data management, each service plays a pivotal role. This architecture adapts and evolves to accommodate new features, showcasing its commitment to innovation and user satisfaction.
