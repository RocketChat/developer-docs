---
description: The Pre-Requisites for developing a Rocket.Chat App
---

# Apps Engine Environment Setup

The Rocket.Chat Apps Engine is built on top of Node.js VM module, which means the majority of the environment setup will be around running that module within your RC workspace.

Setting up the development environment requires you to download and install multiple dependencies. You will need an active internet connection throughout the process.

## Requirements

You are required to have the following installed already on your machine before starting. If you don't, please take a minute and get them ready.&#x20;

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org) (Version 12 and above)
* [Rocket.Chat Apps Engine CLI](../rocket.chat-app/rocket.chat-app-engine-cli.md#installation)
* [Yarn](http://yarnpkg.com/) is recommended instead of npm.

## Pre-requisites

While using the Apps Engine, we are expecting you to have some basic understanding of a few topics listed below

#### A basic understanding of Command Line

The Rocket.Chat Apps Engine CLI is very basic in terms of its usage but a brief understanding of navigation within the Command Line will be beneficial to understand where the project is leading you.

#### Basic knowledge of TypeScript Development

For writing an App, you need to write and execute [TypeScript](https://www.typescriptlang.org/) code. Although most definitions are handled within the Apps Engine CLI, you need to understand where the code is leading you towards to have a better understanding of how your App interacts with the Rocket.Chat server and external APIs

#### Understanding the Lifecycle methods of Apps Engine and Node.js VM

You'll find below a section explaining the [Lifecycle methods of Apps Engine](../fundamentals-of-apps/app-lifecycle.md#introduction). We highly recommend you reading that before getting started.&#x20;

Additionally, you'll find yourself executing some [Node.js VM](https://nodejs.org/api/vm.html) methods from time to time, hence reading that documentation will be helpful as well.

