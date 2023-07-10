# Dialogflow

Using the Rocket.Chat Dialogflow App, you can set up and train your chatbot to respond to any query it's been trained for and configure it to act as an Omnichannel agent.

{% hint style="info" %}
To set up your [Dialogflow](https://cloud.google.com/dialogflow) agent, visit the [official Dialogflow documentation](https://cloud.google.com/dialogflow/docs).
{% endhint %}

## Install the Dialogflow app

It's recommended to install the Dialogflow app from[ Rocket.Chat marketplace](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/dialogflow-app#install-dialogflow-app).

## How to get Google Credential File or Private key file

To connect to your Dialogflow agent, the Dialogflow app requires the  following credentials:

* Project Id&#x20;
* Client email&#x20;
* Private Key

After creating a service account and private key on your [Google Cloud Console](https://console.cloud.google.com/), download the JSON file containing the key. The file contains all the necessary credentials needed.

## Set up Dialogflow

* Navigate to **Administration > Workspace > Users** and create a new user with the following roles:&#x20;
  * `bot`
  * `livechat-agent`
* Go to **Administration > Workspace > Settings > Omnichannel > Routing** and enable **Assign new conversations to bot agent**.
* On the **Dialogflow App Info** screen, navigate to **Settings.**
* Update the required fields:
  * **Bot Username:** Set the username of the bot you created earlier.
  * **Project Id:** The `project_id` property of the Google credentials file.
  * **Environment:** The [environment](https://cloud.google.com/dialogflow/es/docs/agents-versions) where the bot is set up.
  * **Client Email:** The `client_email`  property of the Google credentials file.
  * **Private Key:** The `private_key` property of the Google credentials file.
  * **Language:** Select the language you'd be interacting with the Bot.
  * **Fallback Responses Limit:** If the Omnichannel end-user asks something that the bot is not trained to answer and fails. **Fallback Responses Limit** defines how many failures of the conversation should be forwarded to a human agent.
  * **Target Department for Handover:** Select the department to transfer customers when there is a bot-to-live agent handover.
  * **Handover Message:** A message sent to the customer upon handover.
  * **Service Unavailable Message:** A message sent by the bot to the customer if service is unavailable.
  * **Close Chat Message:** A message sent automatically to the customer when a chat is closed.
  * **Hide Quick Replies:** If enabled, all quick replies will hide when customers click on any of them.
* Click **Save Changes**.

You can test your Dialogflow Connection by viewing your app log.&#x20;

To view your app log,&#x20;

* Click the kebab menu on the **Dialogflow App Info** screen and select **View Logs**.&#x20;
* Select the recent **onSettingUpdated** tile. If there is `Google Credentials validation Success`, your setup is good to go. If otherwise, then recheck your Dialogflow credentials.

## Adding Quick Replies support to your Dialogflow Bot

* To add quick Replies, use  `Custom-Payload` for Responses on Dialogflow Console.&#x20;
* Go to **Intent > Responses > Add Responses > Custom Payload.**&#x20;
* Add the `Quick Replies` you want, following [the structure format in the repository](https://github.com/RocketChat/Apps.Dialogflow/blob/master/docs/QuickReplies.md).
