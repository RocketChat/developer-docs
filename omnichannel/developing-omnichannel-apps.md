# Developing Omnichannel Apps

One of the best ways of utilizing omnichannel features is through building interactive [RocketChat Apps.](https://developer.rocket.chat/apps-engine/rocketchat-app)

For more information on building the RocketChat Apps, see [https://developer.rocket.chat/apps-engine/getting-started](https://developer.rocket.chat/apps-engine/getting-started).

## Key Traits in Omnichannel Apps

Most omnichannel apps make use of these recipes and components.

### Recipes

{% embed url="https://github.com/RocketChat/Rocket.Chat.Apps-engine/blob/alpha/README.md" %}
App-Engine README
{% endembed %}

### Components

1.  **A Webhook Endpoint**: This is where channels like WhatsApp, Facebook, or any external source will trigger message events when a visitor sends messages using those channels.

    You can register an App endpoint following the guide [https://developer.rocket.chat/apps-engine/sample-app-snippets/registering-api-endpoints](https://developer.rocket.chat/apps-engine/sample-app-snippets/registering-api-endpoints) in the Apps section.
2.  **A Livechat Message Handler**: The message handler is called when an agent sends any message on a room, which is then forwarded to the respective channels.

    We have a guide on Apps message handlers here: [https://developer.rocket.chat/apps-engine/getting-started/event-interfaces](https://developer.rocket.chat/apps-engine/getting-started/event-interfaces).
