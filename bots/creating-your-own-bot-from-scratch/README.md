# Creating Your Own Bot From Scratch

This document outlines the steps required to create your first bot with Rocket.Chat.

## Steps to Create a Bot

### 1. Create a bot user

In order to talk to your chatbot, there must be a user account pre-configured on the Rocket.Chat server that the bot can use to log in.

To add user accounts you need to have admin privileges:

* Navigate to **Administration** > **Workspace** > **Users.**
* Click **+New** to create a new user.
* Fill in the user information, verify the user, and assign it a `bot` role.
* Click **Save**

Once saved, the bot's credentials can be configured with the `CHAT_USER` and `ROCKETCHAT_PASSWORD` [environmental variables](../bots-development-environment-setup.md) of your bot.

{% hint style="info" %}
To avoid creating multiple accounts for bot emails, you can use Gmail +`address` alias. For example: `youremail+botnam@gmail.com`. [See this issue for more](https://github.com/RocketChat/Rocket.Chat/issues/7125).
{% endhint %}

### 2. Code your bot

To make the process of coding a bot easier and faster, you may want to check our existing guides below to deploy a basic bot instance quickly. As an advanced alternative, you can create your bot from the scratch using your favorite framework.

{% hint style="info" %}
Developing a [Hubot ](https://github.com/RocketChat/hubot-rocketchat-boilerplate)can serve as a good entry point in learning chatbot principles.
{% endhint %}

{% content-ref url="develop-a-rocket.chat-sdk-bot.md" %}
[develop-a-rocket.chat-sdk-bot.md](develop-a-rocket.chat-sdk-bot.md)
{% endcontent-ref %}

{% content-ref url="develop-a-botpress-bot.md" %}
[develop-a-botpress-bot.md](develop-a-botpress-bot.md)
{% endcontent-ref %}

### 3. Talk to your bot

{% hint style="success" %}
If the bot is configured to listen to direct messages (`RESPOND_TO_DM=true`), and messages are prepended with `BOT_NAME` or a preconfigured `BOT_ALIAS`, the bot will _usually_ respond to all messages addressed directly to the bot user (depending on the particular bot framework).
{% endhint %}
