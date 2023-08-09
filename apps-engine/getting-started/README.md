# Getting Started with Apps Engine

### Setting up Apps Engine development environment&#x20;

This document describes the requirements for developing an application using Rocket.Chat's Apps Engine. Consider this a guide for configuring your local workstation for Apps Engine app development.

You have to download and install multiple dependencies in order to set up the development environment. Throughout the entire process, an active Internet connection is required. This section will discuss tools that are beneficial for all developers.

1. **Editors:** You will spend a significant amount of time in front of a text editor if you undertake any type of development. There are numerous languages for web computing, with JavaScript being one of the most prevalent. Visual Studio Code (or VSCode) is a free and simple-to-use editor.
2. **Version Control and Repository Manager:** You will need a system to monitor code modifications (version control) and a location to store your code (a repository manager, or repo manager). Git can be used for version control, while GitHub can be used to manage the repository.
3. **Server Management and Package Manager:** To develop a full-stack JavaScript application, a server-side JavaScript runtime is required. Additionally, you will need a package manager. You can use Node.js as your server environment, as it can serve files and connect to your database using JavaScript. As for the Package Manager, we recommend using yarn because it can install libraries more quickly and is a secure, dependable JavaScript dependency management tool.
4. **Database:** You need a database to store your application data. The Rocket.Chat server uses MongoDB as a database to store all chat messages, user information, and other system configurations and related data.

### About Node.js vm module

Node.js is a cross-platform, open-source JavaScript runtime environment that is extensively used to develop server-side and networking applications. Node.js is designed on top of Chrome's V8 engine, allowing developers to run Javascript programs exceptionally quickly by compiling them directly to machine code. The VM module is a fundamental feature of Node.js that allows developers to execute programs in a virtual machine (VM) context. The VM module provides access to APIs for compiling and executing code within the context of a V8 virtual machine. The Rocket.Chat Apps Engine is built on top of the Node.js VM module; therefore, the majority of the environment configuration will involve launching the VM module within your Rocket.Chat workspace.

#### What is context?&#x20;

With the help of the VM module, a context is essentially an alternative environment that is created. This environment consists solely of key-value pairings, each of which runs directly on top of the V8 engine.

The primary motivation behind the Node.js VM module was to isolate each app on its own scope, effectively preventing them from interacting directly with the host Rocket.Chat server or other apps, so they couldn't inject data and disrupt the system or expose data from other sources. In addition, it is also to spare us the complication of spawning, controlling, and managing the communication of external processes in order to execute these logics. This was the project's foundation, and it allowed us to concentrate our efforts on enabling applications to customize their experience within our platform via a controlled API.

