# Omnichannel Environment Setup

The RocketChat omnichannel feature provides a multi-channel environment for communication between companies and their customers.

## Requirements

Before you set up LiveChat, you are required to have the following installed on your device.

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [Yarn](http://yarnpkg.com/) is recommended instead of npm.

## Setting Up LiveChat

The Rocket.Chat LiveChat platform is developed with [Preact](https://preactjs.com/). It is a minimal, lightweight application designed to facilitate B2C (Business-to-customer) communication between Agents and website visitors.

{% hint style="info" %}
This setup is done assuming you have a Rocket.Chat server running. We will use a local instance at `http://localhost:3000` for this guide.
{% endhint %}

To set up OmniChannel LiveChat,

* Clone the LiveChat source code from the [GitHub repository](https://github.com/RocketChat/Rocket.Chat/tree/develop/packages/livechat) by running this command:

```bash
git clone https://github.com/RocketChat/Rocket.Chat.git
```

* Navigate to the LiveChat folder in the cloned directory.

<pre class="language-bash"><code class="lang-bash">cd Rocket.Chat
<strong>cd packages/livechat
</strong></code></pre>

* Install dependencies by running

```bash
yarn
```

{% hint style="info" %}
You can check the recommended version of _node_ and _yarn_ in the `package.json` file in the root directory.
{% endhint %}

* Build preact application to `/build` folder after executing.

```bash
yarn dev
```

* In another terminal, run webpack with hot reload at `http://localhost:8080` by executing this command:

```bash
yarn start
```

* Open up the `widget-demo.html` file in your browser: `http://localhost:8080/widget-demo.html`. You should see a page with the LiveChat initiation icon at the bottom right.

![](<../.gitbook/assets/image (51) (1).png>)

![](<../.gitbook/assets/image (65) (1).png>)

{% hint style="info" %}
For better performance, you can run this `widget-demo.html` on an [HTTP server](https://github.com/http-party/http-server).
{% endhint %}
