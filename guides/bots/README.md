# Bots Guides

![Rocket.Chat Bots Banner](../../.gitbook/assets/banner.png)

## What are bots in Rocket.Chat?

Bots \(or Chatbots\) are pieces of software or software systems that provide automated messaging to a chat platform. They typically add value by integrating large external services such as CRM and big data sources. Bots provide a friendly conversational interface that users on chat platforms are already familiar with, which also brings simplicity to complex systems. Besides, bots add automation, natural language understanding, and machine learning possibilities.

In Rocket.Chat, a bot is a special user account with the `bot` role and a specific set of permissions.

## How do bots send and receive messages?

Bots in Rocket.Chat cannot send messages to users on their own. Instead, they subscribe to so-called collections of messages that every user has. The subscription creates a stream that is updated every time messages are sent either directly to bots or any room they are joined in.

For more details, see the [Bots Architecture section](bots-architecture.md#message-streams).

## How are bots hosted?

Like most chatbot platforms, Rocket.Chat supports bots that are hosted outside of your Rocket.Chat instance, running on an external server.

For more details, see the [Bots Architecture section](bots-architecture.md#bot-platforms-and-frameworks).

## Are there different types of Bots?

All bots share the common properties described above. However, historical evolution driven by user and business demand has segregated bots into two major distinct categories:

* chat-ops bots  Typically deployed in team-chat or group-chat environments to facilitate the operation of external systems \(such as a development shop's CI pipelines,  gitlab/github builds, etc\).  These bots will report on status of workflows and empower chat users to trigger or control operational workflows on these external systems. Chat-ops bots link _chat_  to _operations_.  
* omnichannel bots  Typically backed by big data, CRMs, as well as machine learning engines to facilitate or supplement customer facing workflows and functions. These bots are deployed across channels \(works in live chat, as readily as Whatsapp, as readily as Apple Business Chat; and works in harmony with human service agents\) to carry our their tasks.  

## Getting Started

These are the basic steps for using bots with Rocket.Chat:

1. A bot user is [created by an admin](create-and-run-a-bot/) on the server;
2. The bot is running as [a separate process](bots-architecture.md) using your chosen framework or platform;
3. The bot environment is pre-configured with [environment variables](configure-bot-environment.md);
4. The bot's behavior is defined via scripts according to the requirements of your framework. For example, check the details on how to [run a bBot bot](running-a-bbot-bot.md).

## Next steps

Get yourself familiar with [Bots Architecture](bots-architecture.md).

## Quick Links

* [Configure the Bot Environment](configure-bot-environment.md)
* [Create a Bot](create-and-run-a-bot/)
* [Running a Botkit Bot](create-and-run-a-bot/botkit-bot.md)
* [Running a Hubot Bot](create-and-run-a-bot/hubot-bot.md)
* [Running a Botpress Bot](create-and-run-a-bot/botpress-bot.md)
* [Running a Rasa Bot](create-and-run-a-bot/rasa-bot.md)
* [Running a bBot Bot](running-a-bbot-bot.md)

## References

Configuration and implementation details for components of the [Bots Architecture](bots-architecture.md) can be found in their project READMEs:

* [Rocket.Chat JS SDK](https://github.com/RocketChat/Rocket.Chat.js.SDK/)
* [bBot Rocket.Chat boilerplate](https://github.com/Amazebot/bbot-rocketchat-boilerplate)
* [Hubot Rocket.Chat boilerplate](https://github.com/RocketChat/hubot-rocketchat-boilerplate/)
* [Hubot Rocket.Chat adapter](https://github.com/RocketChat/hubot-rocketchat/tree/develop/)

## Contribute

To contribute to features under development see our [Bots Project issues](https://github.com/RocketChat/Rocket.Chat/projects/16).

