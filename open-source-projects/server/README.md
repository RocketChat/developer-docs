# Server

The Rocket.Chat Server is a secure and scalable communication platform among Rocket.Chat open source projects. It is responsible for providing the core functionality of Rocket.Chat. It is built using modern web technologies, such as Node.js, MongoDB, and Meteor, and is designed to be scalable and secure for organizations of various sizes. This guide focuses on the essential server-side features that power many Rocket.Chat capabilities.&#x20;

[Rocket.Chat clients](https://docs.rocket.chat/setup-and-configure/installing-client-apps) use **APIs** and **websockets** to communicate with the server in real-time, giving users a seamless experience. It stores data in MongoDB, a NoSQL database. Files can be stored locally on the server or on a network service like Amazon S3. For more information on how these components interact, please see [architecture-and-components.md](../../getting-started/architecture-and-components.md "mention"). Rocket.Chat also supports various deployment methods including Docker and AWS.&#x20;

{% hint style="info" %}
For detailed information on deployments, please refer to the [official deployment guide](https://docs.rocket.chat/deploy/prepare-for-your-deployment).
{% endhint %}

&#x20;The Rocket.Chat server code can be found on [GitHub](https://github.com/RocketChat/Rocket.Chat).

{% hint style="info" %}
See the [repository-structure.md](repository-structure.md "mention") guide to dive deeper into the code structure.
{% endhint %}

The Rocket.Chat Server is an open-source, highly customizable, and extensible platform that allows developers to contribute and develop custom and new functionalities. With a deep understanding of the server's role and capabilities, developers can more effectively contribute to and utilize Rocket.Chat's services. This knowledge will remain valuable as the project evolves, ensuring that all stakeholders can fully participate in and benefit from this remarkable open-source platform.

{% hint style="info" %}
To learn more about contributing to Rocket.Chat, see [participate-in-rocket.chat-development](../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/ "mention").
{% endhint %}
