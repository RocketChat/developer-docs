# Chatbots

You can build several **Chatbot apps** for your Rocket.Chat workspace to assist your customers and automate certain customer support activities within your business. They can be considered an [agent ](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents)who is 24/7 active. A typical example includes the [Dialogflow](https://github.com/RocketChat/Apps.Dialogflow) and [Rasa](https://github.com/RocketChat/Apps.Rasa) apps.

These apps enhance conversational experiences for your users. It can send quick reply buttons to your customers when an [agent](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) has not replied to their message.

{% hint style="info" %}
They work with all [channel apps](channel-apps.md).
{% endhint %}

They utilize event handlers provided by the [Rocket.Chat app engine](broken-reference), particularly the [executePostMessageSentHandler](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/messages\_ipostmessagesent.ipostmessagesent.html), to listen to visitors' messages and then forward those messages to respective services like Dialogflow/Rasa. Once a response is received from these services, the applications send the response back to the Rocket.Chat room where the conversation with the visitor is taking place.&#x20;

Some existing **Chatbots apps** in the [Rocket.Chat Marketplace](https://www.rocket.chat/marketplace) includes:

* [**Rasa**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/rasa-app)
* [**Dialogflow**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/dialogflow-app)
