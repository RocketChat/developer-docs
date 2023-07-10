# Rasa

The Rasa app facilitates the integration of your [Rasa bot](https://rasa.com/) with Rocket.Chat, enabling you to handle conversations from multiple channels through a single Rasa bot.&#x20;

{% hint style="info" %}
To set up your Rasa server, visit the [Rasa installation guide](https://rasa.com/docs/rasa/).
{% endhint %}

## Rasa app operation modes

The Rasa app operates in two modes: Synchronous and Asynchronous modes.

### Synchronous Mode

The app utilizes Rasa's [REST API](https://rasa.com/docs/rasa/user-guide/connectors/your-own-website/#restinput) to exchange messages in synchronous mode. To enable this mode, configure the Rasa bot's `credentials.yml` file and enable the REST API.

### Asynchronous / Callback Mode

In asynchronous mode, the app utilizes [callbacks](https://rasa.com/docs/rasa/connectors/your-own-website/#callbackinput) to receive messages from Rasa. It is helpful if your app uses features like [Reminders and External events](https://rasa.com/docs/rasa/reaching-out-to-user/#reminders-and-external-events), as they only work in this mode. To configure Rasa for this mode, you need to include the following configuration in the `credentials.yml` file of your Rasa server:

```yaml
callback:
  url: "<your-callback-url"
```

{% hint style="info" %}
To get your app callback URL, navigate to the **Rasa App Info > Details > APIs** on your workspace**.**
{% endhint %}

## Install Rasa App

It's recommended to install the Rasa app from the[ Rocket.Chat marketplace](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/rasa-app#install-rasa-app).

## Set up Rasa App

* Navigate to **Administration > Workspace > Users** and create a new user with the following roles:&#x20;
  * `bot`
  * `livechat-agent`
* Go to **Administration > Workspace > Settings > Omnichannel > Routing** and enable **Assign new conversations to bot agent**.
* On the **Rasa App Info** screen, navigate to **Settings.**
* Update the required fields:
  * **Bot Username:** Set the username of the bot you created earlier. This is the user who will assist with the conversations through Rasa integration.
  * **Rasa Server URL:** The URL of your Rasa server _(for example — http://localhost:5005)._
  * **Service Unavailable Message:** A message sent to your customer if service is unavailable.
  * **Close Chat Message:** A message sent to your customer when a conversation is closed.
  * **Handover Message:** A message sent to a customer upon handover.
  * **Default Handover Department Name:** The target department name where you want to transfer the customer upon handover.&#x20;
  * **Enable Callbacks:** Enable callbacks to allow the app to use only callback messages. It is useful when you are using reminder messages in your RASA bot.
  * **Hide Quick Replies:** If enabled**,** all quick replies will hide when customers click on any of them.
* Click **Save Changes**.

## Adding Quick Replies support to your Rasa Bot

Rasa App provides out-of-the-box support for quick replies to improve customer conversations. To add quick replies, you can follow the structure of the [rich responses](https://rasa.com/docs/rasa/responses/#rich-responses) defined in Rasa.
