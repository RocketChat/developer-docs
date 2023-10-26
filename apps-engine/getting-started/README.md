# Getting Started with Apps-Engine

### Prerequisites

Before beginning, the following must be installed on your machine:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org/en) (version 12 and above)&#x20;
* Rocket.Chat [Apps-Engine CLI](rocket.chat-app-engine-cli.md)
* A code editor. We recommend Visual Studio Code (VSCode).
* A local [development instance](https://docs.rocket.chat/deploy/prepare-for-your-deployment/rapid-deployment-methods/docker-and-docker-compose) of Rocket.Chat must be running on your system.

To develop a Rocket.Chat App, you must write [TypeScript](https://www.typescriptlang.org/) code. Although the majority of definitions are managed by the Apps-Engine CLI, you must grasp where the code guides you in order to comprehend how your application interacts with the Rocket.Chat server and external APIs.

### **About Rocket.Chat Server**

To test your applications, you will need a server that is active. Ideally, this would be a test environment, so as not to impact the production environment. The following components are related to the Rocket.Chat server, and there is no action required from your end:&#x20;

* **Server Management and Package Manager:** To develop a full-stack JavaScript application, a server-side JavaScript runtime is required. Additionally, you will need a package manager. You can use Node.js as your server environment, as it can serve files and connect to your database using JavaScript. As for the Package Manager, we recommend using Yarn because it can install libraries more quickly and is a secure, dependable JavaScript dependency management tool.
* **Database:** You need a database to store your application data. The Rocket.Chat server uses MongoDB as a database to store all chat messages, user information, and other system configurations and related data.

### About Node.js VM Module

Node.js is a cross-platform, open-source JavaScript runtime environment that is extensively used to develop server-side and networking applications. Node.js is designed on top of Chrome's V8 engine, allowing developers to run Javascript programs exceptionally quickly by compiling them directly to machine code.&#x20;

The virtual machine (VM) module is a fundamental feature of Node.js that allows developers to execute programs in a VM context. The VM module provides access to APIs for compiling and executing code within the context of a V8 VM. The Rocket.Chat Apps-Engine is built on top of the Node.js VM module; therefore, the majority of the environment configuration will involve launching the VM module within your Rocket.Chat workspace.

#### About Context&#x20;

With the help of the VM module, a context is an alternative environment that is created. This environment consists solely of key-value pairings, each of which runs directly on top of the V8 engine.

The aim of using the Node.js VM module was to isolate each app on its own scope, preventing them from interacting directly with the host Rocket.Chat server or other apps, so they couldn't inject data and disrupt the system or expose data from other sources. In addition, it is also to avoid the complication of spawning, controlling, and managing the communication of external processes in order to execute these logics.

{% hint style="info" %}
**Note:** The app doesn't have direct access to the VM's APIs. This information is for your understanding.
{% endhint %}
