---
description: The Pre-Requisites for developing a Rocket.Chat App
---

# Apps Engine Environment Setup

The Rocket.Chat Apps Engine is built on top of Node.js VM module, which means most of the environment setup will be around running that module within your RC workspace.

Setting up the development environment requires you to download and install multiple dependencies. You will need an active internet connection throughout the process.

## Requirements

You must have the following installed already on your machine before starting. If you don't, please take a minute and get them ready.

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org) (version 12 and above)
* [Rocket.Chat Apps Engine CLI](rocket.chat-app-engine-cli.md#installation)
* [Yarn](http://yarnpkg.com/) (recommended instead of npm)

## Pre-requisites

While using the Apps Engine, we expect you to have a basic understanding of a few topics listed below.

#### A basic understanding of Command Line

The Rocket.Chat Apps Engine CLI is very basic in terms of its usage. Still, a brief understanding of navigation within the Command Line will be beneficial to understanding where the project is leading you.

#### Basic knowledge of TypeScript Development

For writing an App, you need to write and execute [TypeScript](https://www.typescriptlang.org/) code. Although most definitions are handled within the Apps Engine CLI, you need to understand where the code leads you to know how your App interacts with the Rocket.Chat server and external APIs.

#### Understanding the Lifecycle methods of Apps Engine and Node.js VM

You'll find here a section explaining the [Lifecycle methods of Apps Engine](understanding-app-lifecycle.md#introduction). We highly recommend you read it before getting started.

Additionally, you'll find yourself executing some [Node.js VM](https://nodejs.org/api/vm.html) methods from time to time. Hence reading that documentation will be helpful as well.
