# Omnichannel Environment Setup

The RocketChat omnichannel feature provides a multi-channel environment for communication between companies and their customers.

## Setting Up LiveChat

The Rocket.Chat LiveChat platform, is developed with [Preact](https://preactjs.com).

It altogether is a very small lightweight application designed to facilitate B2C (Business-to-customer) communication between Agents and website visitors.

{% hint style="info" %}
This setup is done assuming you have a Rocket.Chat server running. We will use a local instance at [http://localhost:3000](http://localhost:3000).
{% endhint %}

### Requirements

You are required to have the following installed already on your machine before starting. If you don't, please take a minute and get them ready.&#x20;

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [Yarn](http://yarnpkg.com) is recommended instead of npm.

### Get the LiveChat Code

Open up your terminal/command line and navigate or `cd` into your working directory and clone the LiveChat source code from[ our repository](https://github.com/RocketChat/Rocket.Chat.Livechat) by executing the following script

```
cd ./working-directory
git clone https://github.com/RocketChat/Rocket.Chat.Livechat.git
```

### Run the LiveChat Code

1. Navigate into the cloned directory and install the dependencies by running

```bash
cd Rocket.Chat.Livechat
yarn
```

&#x20; 2\. Build preact application to `/build` folder after executing

```
yarn dev
```

&#x20;In another terminal, run webpack with hot reload at [http://localhost:8080](http://localhost:8080) by executing

```
yarn start
```

Open up the `widget-demo.html` file in your browser: `http://localhost:8080/widget-demo.html`

You should see a page with the LiveChat initiation icon at the bottom right.

![](<../.gitbook/assets/image (51).png>)

![](<../.gitbook/assets/image (65).png>)

{% hint style="info" %}
For better performance, you can run this `widget-demo.html` on an [HTTP server](https://github.com/http-party/http-server).
{% endhint %}
