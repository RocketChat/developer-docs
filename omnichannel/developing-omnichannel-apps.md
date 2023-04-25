# Developing Omnichannel Apps

Building interactive [RocketChat Apps](https://developer.rocket.chat/apps-engine/rocket.chat-apps-and-apps-engine) is one of the most effective ways to utilize omnichannel features. To learn more about building Rocket.Chat Apps, see [getting-started](../apps-engine/getting-started/ "mention").

## Key Traits in Omnichannel Apps

Most omnichannel apps make use of these recipes and components.

### Recipes

{% embed url="https://github.com/RocketChat/Rocket.Chat.Apps-engine/blob/alpha/README.md" %}
App-Engine README
{% endembed %}

### Components

* **A Webhook Endpoint**: When a visitor sends messages through channels like WhatsApp, Facebook, or any other external source, this is where those channels' message events will be triggered. You can register an App endpoint following the [Registering API endpoints](https://developer.rocket.chat/apps-engine/building-custom-apps/sample-app-snippets/registering-api-endpoints) guide.&#x20;
* **A Livechat Message Handler**: When an agent sends a message on a room, the message handler is invoked, and the message is then sent to the appropriate channels.

{% hint style="info" %}
To learn more about App message handlers, see [event-interfaces.md](../apps-engine/fundamentals-of-apps/event-interfaces.md "mention").
{% endhint %}
