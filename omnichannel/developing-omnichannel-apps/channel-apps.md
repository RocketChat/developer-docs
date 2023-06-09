# Channel Apps

The channel apps allow you to connect to external channels like WhatsApp, FB Messenger, etc. With the help of these apps, you can have customer service agents on your workspace assist your customers through these external channels.

For example, customers can message your business on WhatsApp inquiring about a support ticket issue, and the agent on your Rocket.Chat workspace can confirm and update them on the ticket's status while they receive the updates via Whatsapp.

The agent will send notifications on RC, which will be forwarded to WhatsApp via WhatsApp's channel app. The app uses the app's engine's event handlers (namely [executePostMessageSentHandler](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/messages\_ipostmessagesent.ipostmessagesent.html)) to listen to the agent's responses. Similarly, messages from WhatsApp will be forwarded to WhatsApp's channel app via WhatsApp webhook and the app will forward the message to the respective RC channel.
