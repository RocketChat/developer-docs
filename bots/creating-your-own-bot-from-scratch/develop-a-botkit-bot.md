# Develop a Botkit Bot

[Botkit](https://github.com/howdyai/botkit) is the leading developer tool for building chatbots, apps, and custom integrations for major messaging platforms.

Botkit offers everything you need to design, build and operate an app:

* Easy-to-extend starter kits;
* Fully-featured SDK with support for all major platforms;
* [Tons of plugins and middlewares](https://github.com/howdyai/botkit-docs/blob/master/docs/readme-middlewares.md)

In addition, Botkit works with all the NLP services (like Microsoft LUIS and IBM Watson), it can use any type of database and runs on almost any hosting platform.

### Botkit Integration Architecture

![](<../../.gitbook/assets/image (99).png>)

## Botkit Quick Start Guide

Botkit is a Node.js module and works with Node and npm.

The fastest way to start with Botkit is using [botkit-starter-rocketchat](https://github.com/RocketChat/botkit-starter-rocketchat):

### Get the Botkit Bot Boilerplate Code

* Open up the terminal in the directory you wish to develop your bot in and run the following commands to fetch from our repository and install all dependencies

```
git clone https://github.com/RocketChat/botkit-starter-rocketchat
cd botkit-starter-rocketchat/
npm install
```

* Next, create a `.env` file in the working directory if it doesn't exist and fill it with the following configurations. Rename to match your details

```
# Environment Config

# store your secrets and config variables in here
# only invited collaborators will be able to see your .env values
# reference these in your code with process.env.SECRET

# Specify a Botkit Studio token so your bot can access cloud-hosted content and features
# Get one here: https://studio.botkit.ai/
studio_token=''

# Specify your instance of RocketChat
ROCKETCHAT_URL='http://localhost:3000'

# Specify the bot user name in RocketChat
ROCKETCHAT_USER='botkit.user'

# Specify the bot user password in RocketChat
ROCKETCHAT_PASSWORD='botkit'

# Specify with true or false the usage of SSL
ROCKETCHAT_USE_SSL=false

# Specify the list of public rooms that the bot will be added.
# Add channels like this: 'GENERAL, channel2, ...'
ROCKETCHAT_ROOM='GENERAL'

# Specify the channels that the bot only can answer when mentioned.
# The bot will answer all messages for default, add channels like this:
# 'GENERAL, channel2, ...'
MENTION_ROOMS='GENERAL'

# Specify if the bot it's allowed to answer direct messages
RESPOND_TO_DM=true

# Specify if the bot it's allowed to answer live chat messages
RESPOND_TO_LIVECHAT=true

# Specify if the bot it's allowed to answer edited messages
RESPOND_TO_EDITED=true

# Enable learning mode, a set of features
# that allows your bot to update itself using Botkit Studio's API
LEARNING_MODE=true

```

* When the configuration is done, run the following script to start the bot

```
npm start
```

* After executing the command, botkit will try to connect to the Rocket.Chat instance and then will listen to messages in `general` room

```
$ npm start

> botkit-starter-rocketchat@0.0.1 start C:\Users\COMPUTER^CARE\Desktop\RocketChat\Bots\botkit-starter-rocketchat
> node bot.js

~~~~~~~~~~
Botkit Studio Starter Kit
You probably forgot to update your environment variables
Get a Botkit Studio token here: https://studio.botkit.ai/
~~~~~~~~~~
Initializing Botkit v0.6.16
info: ** No persistent storage method specified! Data may be lost when process shuts down.
debug: Setting up a handler for spawned
debug: Setting up a handler for heard_trigger
debug: Setting up a handler for command_triggered
debug: Setting up a handler for remote_command_end
debug: Setting up a handler for direct_message 
debug: Setting up a handler for live_chat      
debug: Setting up a handler for channel        
debug: Setting up a handler for private_channel
[connect] Connecting {    
  username: 'botkit.user',
  password: '12345',      
  ldap: false,
  host: 'localhost:3000', 
  useSsl: false,
  timeout: 20000,
  rooms: [ 'GENERAL' ],   
  allPublic: false,
  dm: true,
  livechat: true,
  edited: true,
  integrationId: 'js.SDK',
  roomCacheMaxSize: 10,
  roomCacheMaxAge: 300000,
  dmCacheMaxSize: 10,
  dmCacheMaxAge: 100000
}
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
debug: Setting up a handler for sticker_received
debug: Setting up a handler for image_received
debug: Setting up a handler for audio_received
debug: Setting up a handler for heard_trigger
debug: Setting up a handler for conversationStarted
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
debug: Setting up a handler for message_received
~~~~~~~~~~
NOTE: Botkit Studio functionality has not been enabled
To enable, pass in a studio_token parameter with a token from https://studio.botkit.ai/
[connect] Connected
[login] Logging in botkit.user
[getRoomIdByNameOrId] Calling (caching): GENERAL
[getRoomIdByNameOrId] Success: "GENERAL"
[joinRoom] Calling (async): ["GENERAL"]
[joinRoom] Success: true
[subscribe] Preparing subscription: stream-room-messages: __my_messages__
[subscribe] Stream ready: 4
[reactive] Listening for change events in collection stream-room-messages
```

* After running the bot, Log in to the server as a regular user (not the BOT user), go to `general` room, and try to talk to your bot. The bot will listen to every message in the channel.

```
[received] Message in room GENERAL
Message receive callback ID Nhbc6R84s24ahHwiM at Wed Nov 24 2021 10:56:07 GMT+0100 (West Africa Standard Time)
[Incoming] rodriq: hello
[getRoomNameById] Calling (caching): GENERAL
[getRoomNameById] Success: "general"
I RECEIVED {
  _id: 'Nhbc6R84s24ahHwiM',
  rid: 'GENERAL',
  msg: 'hello',
  ts: 1637747767569,
  u: { _id: '5y8XK9YBhCHBDL4rx', username: 'rodriq', name: 'Rodriq' },
  _updatedAt: { '$date': 1637747767627 },
  urls: [],
  mentions: [],
  channels: [],
  md: [ { type: 'PARAGRAPH', value: [Array] } ],
  type: 'message_received',
  raw_message: {
    _id: 'Nhbc6R84s24ahHwiM',
    rid: 'GENERAL',
    msg: 'hello',
    ts: { '$date': 1637747767569 },
    u: { _id: '5y8XK9YBhCHBDL4rx', username: 'rodriq', name: 'Rodriq' },
    _updatedAt: { '$date': 1637747767627 },
    urls: [],
    mentions: [],
    channels: [],
    md: [ [Object] ],
    type: 'message_received'
  },
  _pipeline: { stage: 'receive' },
  text: 'hello',
  user: 'rodriq',
  channel: 'GENERAL'
}
debug: RECEIVED MESSAGE
```

![Botkit bot is talking](../../.gitbook/assets/botkit.gif)

### Running Botkit with Docker

To fire up a docker instance of your botkit bot, run the following command.

```
docker-compose up mongo rocketchat
```
