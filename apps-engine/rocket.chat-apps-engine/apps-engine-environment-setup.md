# Apps Engine Environment Setup

Before beginning, the following must be installed on your machine:&#x20;

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org/en) (version 12 and above)&#x20;
* Rocket.Chat Apps Engine CLI&#x20;
* [Yarn](https://yarnpkg.com/)&#x20;

Git, Node.js, and Yarn have been covered in the preceding sections. The Apps Engine CLI will be elaborated upon in forthcoming documents.

We recommend that you [install Visual Studio Code](https://code.visualstudio.com/download). In addition, a local [development instance](https://docs.rocket.chat/deploy/prepare-for-your-deployment/rapid-deployment-methods/docker-and-docker-compose) of Rocket.Chat must be running on your system.

We expect you to have a fundamental understanding of the topics outlined below while using Apps Engine.

### Command Line

The Rocket.Chat Apps Engine CLI is extremely basic and easy to use. However, a basic understanding of Command Line navigation would be advantageous.

### TypeScript Development&#x20;

To develop an application, you must write and execute [TypeScript](https://www.typescriptlang.org/) code. Although the majority of definitions are managed by the Apps Engine CLI, you must grasp where the code guides you in order to comprehend how your application interacts with the Rocket.Chat server and external APIs.

### Lifecycle methods of Apps Engine and Node.js VM&#x20;

Our documentation contains a section detailing the Apps Engine lifecycle methods. We highly recommend you read it before beginning.

In addition, you will occasionally discover yourself executing Node.js VM methods. Consequently, perusing [this documentation](https://nodejs.org/api/vm.html) will also be beneficial.
