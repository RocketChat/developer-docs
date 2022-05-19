---
description: >-
  The framework that enables users to create and host their own Rocket.Chat
  Apps.
---

# Rocket.Chat Apps Engine

The Rocket.Chat Apps-Engine is the framework that allows for the development of Rocket.Chat Apps. It provides the APIs for Rocket.Chat Apps to interact with the host system. These apps allow for a tighter integration with whatever workflow our users follow. It also covers most, if not all, things that incoming/outgoing integrations and bots do. Interestingly, it has some cool features, like adding interactive buttons to messages and opening modals (checkout [Poll](https://docs.rocket.chat/guides/app-guides/poll) for a showcase) and more!

#### Currently, a Rocket.Chat App can:

* Listen to message events
  * before/after sent
  * before/after updated
  * before/after deleted
* Listen to room events
  * before/after created
  * before/after deleted
* Send messages to users and livechat visitors
* Register new slash commands
* Register new HTTP endpoints

Some features the Engine allows Apps to use:

* Key-Value Storage system
* App specific settings

### Further Topics

{% content-ref url="apps-engine-environment-setup.md" %}
[apps-engine-environment-setup.md](apps-engine-environment-setup.md)
{% endcontent-ref %}

{% content-ref url="contributing-to-apps-engine.md" %}
[contributing-to-apps-engine.md](contributing-to-apps-engine.md)
{% endcontent-ref %}
