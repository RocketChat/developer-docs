# Developing Omnichannel Apps

One of the best ways of utilizing omnichannel features is through building interactive [RocketChat Apps](../apps-engine/rocket.chat-app/).

More details on building RocketChat Apps are covered in [creating-an-app.md](../apps-engine/rocket.chat-app/creating-an-app.md "mention") section.

## Key Traits in Omnichannel Apps

Most omnichannel apps make use of these recipes and components.

### Recipes

{% content-ref url="../apps-engine/recipes/" %}
[recipes](../apps-engine/sample-app-snippets)
{% endcontent-ref %}

### Components&#x20;

1.  **A Webhook Endpoint**: This is where channels like WhatsApp, Facebook, or any external source will trigger message events when a visitor sends messages using those channels.

    You can register an App endpoint following [registering-api-endpoints.md](../apps-engine/recipes/registering-api-endpoints.md "mention") guide in the Apps section.
2.  **A Livechat Message Handler**: The message handler is called when an agent sends any message on a room, which is then forwarded to the respective channels.

    We have a guide on Apps message handlers here [event-interfaces.md](../apps-engine/fundamentals-of-apps/event-interfaces.md "mention").

