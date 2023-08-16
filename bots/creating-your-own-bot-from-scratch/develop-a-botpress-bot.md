# Develop a Botpress Bot

[Botpress](https://botpress.com/) is an on-prem, open-source chatbot-building platform for businesses.

## Botpress Quick Start Guide

Integrate Rocket.Chat with Botpress following this sample

{% embed url="https://github.com/RocketChat/rocketchat-botpress-lab-bot/" %}

## Botpress workflow

This example workflow shows how Botpress can be integrated with Rocket.Chat Omnichannel Live Chat widget.

<figure><img src="../../.gitbook/assets/RocketChat Botpress workflow.png" alt=""><figcaption><p>Rocket.Chat Botpress workflow</p></figcaption></figure>

## Setup

Let us see how to set up a Botpress server and integrate it with a Rocket.Chat workspace.

### Requirements

{% hint style="info" %}
You are required to have a registered workspace and [Omnichannel activated](https://docs.rocket.chat/use-rocket.chat/omnichannel#enable-omnichannel).
{% endhint %}

### Install connector app

To be able to interact with the bot, you need a connector. Follow these steps to get it installed on your Rocket.Chat workspace.

* Navigate to **Administration** > **Workspace** > **Apps**
* Search and install the **Botpress Connector** app by _Luis Hlatki_

### Cloning Example code

* Clone the starter code and enter the directory by running

```bash
git clone https://github.com/RocketChat/rocketchat-botpress-lab-bot.git botpress-lab-bot 
cd botpress-lab-bot
```

{% hint style="info" %}
Edit the `docker-compose.yml` file to remove the `rocketchat` and `mongo` services if you already have a running instance of Rocket.Chat.
{% endhint %}

* Spin up the container with

```bash
docker compose up -d
```

* The botpress dashboard is made available at on port `3001` visit it and configure the admin user
* Import the [bot\_lab.tgz](https://github.com/RocketChat/rocketchat-botpress-lab-bot/blob/main/bot\_lab.tgz) found in the directory cloned above
* Set the bot id as _lab_ and **Import bot**

<figure><img src="../../.gitbook/assets/import botpress bot.png" alt=""><figcaption><p>import botpress bot</p></figcaption></figure>

* Click on the bot to open up then click **Train chatbot** at the bottom right

### Create a bot and agent user

Create the following Rocket.Chat users to be used for the integration

* Navigate to **Administration** > **Workspace** > **Users**
  * Create a **bot user** for the bot with these roles: `bot`, `user`, `livechat-agent` and `livechat-manager`
  * Create an **agent user** with these roles `user` and `livechat-agent`
* Configure the Botpress Connector installed earlier in **Administration** > **Apps** > **Installed** > **Botpress Connector** > **Settings** with the following details:
  * Rocket.Chat bot username: `bot`
  * Botpress bot id: `lab`
  * Botpress server URL: `<http://your-botpress-server-url>`
  * Default handover department: `GENERAL`
  * Then **Save changes**

### Configure Omnichannel

* Navigate to  **Avatar Menu > Omnichannel > Departments**
  * Create a `GENERAL` department and enable it to show on the registration form. Set the `bot` user as an agent
  * Create an `OTHER` omnichannel department, don't enable show on the registration form and set the user agent as an agent

You should have something like below

<figure><img src="../../.gitbook/assets/Omnichannel channel created.png" alt=""><figcaption><p>Omnichannel channel created</p></figcaption></figure>

* Edit the user agent user status to available
* Log in as the bot user and create a PAT (Personal Access Token) without 2 Factor Authentication and copy it. [see this guide](https://docs.rocket.chat/guides/user-guides/user-panel/managing-your-account/personal-access-token)&#x20;

### Configure Botpress settings

Back on your botpress server dashboard, do these settings to complete. This involves setting up details about your Rocket.Chat server.

* Fill in the Rocket.Chat server URL and PATH gotten from above in the `bot.config.json` file at **Dashboard** > **Code Editor** > **Configurations** > **Current Bot** > **bot.config.json** then **Save**

<figure><img src="../../.gitbook/assets/Botpress config file edit.png" alt=""><figcaption><p>Botpress config file edit</p></figcaption></figure>

* Update the transfer room ID with that of the desired department ID in **Dashboard** > **Flows** > **Main Flow** > **transfer-room** node

<figure><img src="../../.gitbook/assets/Edit botpress transfer room.png" alt=""><figcaption><p>Edit botpress transfer room</p></figcaption></figure>

### Testing the Integration

To test the integration,

* Visit `http://<your Rocket.Chat server>/livechat` and start a new Live Chat conversation.
* Optionally you can integrate the [Live Chat widget ](https://docs.rocket.chat/use-rocket.chat/omnichannel/livechat-widget-installation)while taking into consideration the [X-Frame-Options](https://docs.rocket.chat/guides/administration/admin-panel/settings/general)

When successful, you should see something like below

<figure><img src="../../.gitbook/assets/Live Chat widget new conversation.png" alt=""><figcaption><p>Live Chat widget new conversation</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Botpress and Rocket.Chat Live Chat.png" alt=""><figcaption><p>Botpress and Rocket.Chat Live Chat</p></figcaption></figure>
