# Channel Apps

**Channel apps** facilitate the integration of external communication channels, such as WhatsApp and Facebook Messenger, enabling customer service agents to assist customers through these platforms. With the aid of these apps, businesses can establish a connection between their workspace on Rocket.Chat and external channels.&#x20;

For instance, customers can initiate a conversation on WhatsApp to inquire about a support ticket, while the designated [agent ](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents)on the Rocket.Chat workspace can confirm and provide updates regarding the ticket's status. This seamless integration allows agents to efficiently handle customer queries across various channels while ensuring customers receive timely updates through their preferred external platform.

The messages from the [agent](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) on the workspace are forwarded to WhatsApp via the WhatsApp channel app. This integration is facilitated by leveraging the event handlers provided by [Rocket.Chat app engine](broken-reference), particularly the [`executePostMessageSentHandler`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/messages\_IPostMessageSent.IPostMessageSent.html). It listens for the agents' responses and ensures they're seamlessly relayed to Whatsapp. Similarly, incoming messages from WhatsApp are forwarded to the appropriate Rocket.Chat channel via the WhatsApp webhook, with the WhatsApp channel app playing a pivotal role in facilitating this communication flow.

Some existing **Channel apps** in the [Rocket.Chat Marketplace](https://www.rocket.chat/marketplace) includes:

* [**SMS**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/sms)
* [**Telegram**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/telegram-app)
* [**Twitter**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/twitter-app)
* [**Facebook**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/facebook-app)
* [**Instagram**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/instagram-direct)
* [**Whatsapp**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp)
* [**Whatsapp Cloud**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-cloud-app)
* [**Whatsapp Sandbox**](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-sandbox)
