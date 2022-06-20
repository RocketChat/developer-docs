# Creating Your Own Bot From Scratch

This document outlines the steps required to create your first bot with Rocket.Chat.

## Steps to Create a Bot

### 1. Create a bot user

In order to talk to your chatbot, there must be a user account pre-configured on the Rocket.Chat server that the bot can use to log in.

To add user accounts you need to have admin privileges:

* On the top bar, click the three dots (Options) and then click **Administration**
* Select **Users** from the left sidebar
* Click `+` (Add User) button in the right sidebar

![](<../../.gitbook/assets/image (85) (1) (1).png>)

* In the profile window that appears, fill in the _Name_, _Username_, _Email,_ and _Password_ fields
* Enable _Verified_ toggle under the _Email_ field
* Disable _Require password change_ toggle under the _Password_ field
* Select `bot` from the `Add Role` dropdown menu and click _Add Role_ button to the right
* Disable _Join default channels_ and _Send welcome email_ checkboxes
* Click **Save**

Once saved, the bot's credential will be configured with the `HAT_USER` and `ROCKETCHAT_PASSWORD` [environmental variables](../bots-development-environment-setup.md) of your bot.

{% hint style="info" %}
To avoid creating multiple accounts for bot emails, you can use a Gmail +`address` alias. For example: `youremail+botnam@gmail.com`. [See this issue for more](https://github.com/RocketChat/Rocket.Chat/issues/7125).
{% endhint %}

### 2. Code your bot

To make the process of coding a bot easier and faster, you may want to check our existing guides below to deploy a basic bot instance quickly. As an advanced alternative, you can create your bot from the scratch using your favorite framework.

{% content-ref url="develop-a-hubot-bot.md" %}
[develop-a-hubot-bot.md](develop-a-hubot-bot.md)
{% endcontent-ref %}

{% content-ref url="develop-a-botkit-bot.md" %}
[develop-a-botkit-bot.md](develop-a-botkit-bot.md)
{% endcontent-ref %}

{% content-ref url="develop-a-rocket.chat-sdk-bot.md" %}
[develop-a-rocket.chat-sdk-bot.md](develop-a-rocket.chat-sdk-bot.md)
{% endcontent-ref %}

{% content-ref url="develop-a-botpress-bot.md" %}
[develop-a-botpress-bot.md](develop-a-botpress-bot.md)
{% endcontent-ref %}

{% content-ref url="develop-a-rasa-bot.md" %}
[develop-a-rasa-bot.md](develop-a-rasa-bot.md)
{% endcontent-ref %}

### 3. Talk to your bot

If the bot is configured to listen to direct messages (`RESPOND_TO_DM=true`), and messages are prepended with `BOT_NAME` or a preconfigured `BOT_ALIAS`, the bot will _usually_ respond to all messages addressed directly to the bot user (depending on the particular bot framework).
