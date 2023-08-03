# Server Architecture

The architecture of Rocket.Chat Server is designed to be highly scalable, reliable, and flexible. It consists of multiple components that are responsible for different functionalities. Here is an overview of the Rocket.Chat Server Architecture.

{% hint style="info" %}
&#x20;You can get a holistic view of Rocket.Chat's architecture and components [here](../../getting-started/architecture-and-components.md).
{% endhint %}

**Core Server**: This component includes various packages like those responsible for handling user authentication, messaging, and other core functionalities of the Rocket.Chat server.

**Database**: Rocket.Chat server uses MongoDB as a database to store all chat messages, user information, and other system configurations and related data.

**File Storage**: The server also uses a file storage system to store assets, user files, images, and other media files.

## Services

The Rocket.Chat server architecture is composed of both internal and external services. The internal services run within the `meteor` instance and are tightly coupled with the main process, while the external services can run independently in separate processes.

### External Services

Here is a list of the Rocket.Chat External services.

* **Authorization**: This service manages user authorization and permissions, ensuring users have the necessary access rights. It can be horizontally scaled and is stateless.
* **Account**: Responsible for managing user accounts, including the creation, updating, and deletion. It provides methods for user authentication like login and logout. This service is stateless and can be horizontally scaled.
* **Presence**: Handles user presence management, tracking and updating the online status of the user. It can be horizontally scaled and is stateless.
* **StreamHub**: This service captures database changes and broadcasts real-time data to other services. Currently, it does not support horizontal scaling and operates as a single instance service.
* **DDPStreamer**: Manages DDP(Distributed Data Protocol) connections, handling client-server connections, managing subscriptions, and transmitting data to clients. It can be horizontally scaled.
* **AppsEngine**: Responsible for managing apps with Rocket.Chat, including installing, updating, executing, and removal of apps. While it can be horizontally scaled, this service is still under development.

### Internal Services

* **Banner**: Manages banners, including creation, updating, and deletion.
* **LDAP**: Handles LDAP (Lightweight Directory Access Protocol) integration, establishing connections with LDAP servers and managing user synchronization.
* **NPS**: Works in conjunction with the Banner service to manage Net Promoter Score (NPS) surveys, generating banners for selected users and handling responses.
* **Room**: Manages chat rooms, including creation, updating, and deletion.
* **OmniChannel**: Responsible for managing various omnichannel tasks.
* **Omnichannel Voip**: Handles VoIP (Voice over Internet Protocol) calls within the omnichannel system.
* **Team**: Manages teams within Rocket.Chat, including creation, updating, and deletion.
* **UiKitCoreApp**: Manages UI Kit actions and events. It relies on the AppsEngine service for app-related actions and events, as well as Meteor Legacy for core actions.
* **Push**: Handles push notifications, sending them to mobile applications.
* **Upload**: Manages file uploads, including uploading files to the file system and handling file management.
* **Messaging**: Responsible for managing messages within Rocket.Chat.
* **Translation**: ![](../../.gitbook/assets/Deprecated.png) Previously responsible for providing translations to other services, but now deprecated. Translations are provided by the i18n package.
* **Settings**: Manages system settings, including creation, updating, and deletion.
