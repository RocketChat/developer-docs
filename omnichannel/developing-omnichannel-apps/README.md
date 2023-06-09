# Developing Omnichannel Apps

Building interactive [RocketChat Apps](https://developer.rocket.chat/apps-engine/rocket.chat-apps-and-apps-engine) is one of the most effective ways to utilize omnichannel features. To learn more about building Rocket.Chat Apps, see [getting-started](../../apps-engine/getting-started/ "mention").

## Key Traits in Omnichannel Apps

Most omnichannel apps make use of these recipes and components.

### Recipes

{% embed url="https://github.com/RocketChat/Rocket.Chat.Apps-engine/blob/alpha/README.md" %}
App-Engine README
{% endembed %}

On a broad level, you have three categories of omnichannel apps:

1. Channel apps - These are apps that allow you to connect to external channels like WhatsApp, FB Messenger, etc. With the help of these apps, you can have customer service agents on RocketChat assist your customers. For example, Customers can send a message to your business on WhatsApp inquiring about a support ticket issue and the agent can help update them with the ticket's status. The agent will send notifications on RC, which will be forwarded to WhatsApp via WhatsApp's channel app. The app uses the app's engine's event handlers (namely [executePostMessageSentHandler](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/messages\_ipostmessagesent.ipostmessagesent.html)) to listen to the agent's responses. Similarly, messages from WhatsApp will be forwarded to WhatsApp's channel app via WhatsApp webhook and the app will forward the message to the respective RC channel.
2. Chatbot apps - These apps allow you to build chatbots to assist your customers. Examples of these apps include [Dialogflow](https://github.com/RocketChat/Apps.Dialogflow) and [Rasa](https://github.com/RocketChat/Apps.Rasa). These app uses the app's engine's event handlers (namely [executePostMessageSentHandler](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/messages\_ipostmessagesent.ipostmessagesent.html)) to listen to messages from visitors and then forwards those messages to respective services like Dialogflow/Rasa. Upon receiving a response from these services, these apps would send the response back to the RC room.
3. CRM apps - This category of apps is specially built for your omnichannel agents or managers. It helps the agent get quick access to their serving customer's information, past tickets, etc which data is stored in your CRM. We have two such CRM integration on the marketplace right now - Salesforce and Hubspot. Businesses save all their customer information on these CRM platforms and these apps use their API's to query useful information that agents would need for assisting their customers.
