# Architecture and Components

The architecture of Rocket.Chat is based on a client-server model with the server component written in JavaScript using Node.js using the MongoDB database for data storage. It is designed for scalability, high performance, and real-time communication. It can be deployed on-premise or in the cloud, making it suitable for many use cases.

Rocket.Chat provides the following:

* **Authentication:** User authentication and authorization, including user account creation, login, and access control. Administrators can also add other forms of [authentication](https://docs.rocket.chat/setup-and-configure/advanced-workspace-management/authentication), including [LDAP](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/ldap), [SAML](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/saml), and OpenID.
* **Integration**: Enables integrating other systems and services using APIs, webhooks, or different integrations.
* **Notifications**: Sends notifications to mobile devices via push notifications. It also supports SMTP notifications via email.

## Basic Concepts

### Server

The server manages user accounts, message storage, and client communication.

### Client

The client is the user interface that runs on the user's web browser or a mobile application. It communicates with the server using the WebSocket protocol.

### WebSocket

Rocket.Chat uses the WebSocket protocol to enable real-time communication between the client and server. The WebSocket protocol is a high-performance, bi-directional communication protocol that enables instant data transfer.
