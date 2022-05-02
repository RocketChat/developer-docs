# Develop a Hubot Bot

## Hubot Bot Quick Start Guide

The fastest way to start developing a Hubot bot is to use the [Hubot boilerplate](https://github.com/RocketChat/hubot-rocketchat-boilerplate) code we provide. It is a simple Node.js application that requires Hubot and the Rocket.Chat adapter.

The bot can then be executed using a [bin file](https://github.com/RocketChat/hubot-rocketchat-boilerplate/tree/master/bin) in production, or via the package scripts locally using `npm run local` or `yarn local`.

### Get the Hubot Bot Boilerplate Code

Navigate to the folder where you want to work with the bot, open up the terminal and execute the following commands to pull the code and install all the dependecies.

```
git clone https://github.com/RocketChat/hubot-rocketchat-boilerplate
cd hubot-rocketchat-boilerplate
npm install
```

Next, create a `.env` file and enter the configuration information of your bot user.

```
export ROCKETCHAT_URL=myserver.com
export ROCKETCHAT_USER=mybotuser
export ROCKETCHAT_PASSWORD=mypassword
export ROCKETCHAT_ROOM=general
export ROCKETCHAT_USESSL=true
```

Adjust the content to fit your server and user credentials.&#x20;

{% hint style="info" %}
Make sure your bot user(`mybotuser)` has a `bot` role assigned to it.
{% endhint %}

For more information on how to create a bot user please refer to this section.[#1.-create-a-bot-user](./#1.-create-a-bot-user "mention")

Run your code by executing this command

```
source .env
bin/hubot
```

After executing the last command, hubot will try to connect to the Rocket.Chat instance and then will listen to messages in `general` room or any channel specified:

```
$ bin/hubot 
audited 102 packages in 1.798s

2 packages are looking for funding
  run `npm fund` for details      

found 1 low severity vulnerability
  run `npm audit fix` to fix them, or `npm audit` for details
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [startup] Rocket.Chat adapter in use
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [startup] Respond to name: Hubot
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [startup] Respond to alias: hubot.bot
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [connect] Connecting {
  username: 'hubot.bot',
  password: '12345',
  ldap: false,
  host: 'localhost:3000',
  useSsl: false,
  timeout: 20000,
  rooms: [ 'test-bot' ],
  allPublic: false,
  dm: false,
  livechat: false,
  edited: false,
  integrationId: 'js.SDK',
  roomCacheMaxSize: 10,
  roomCacheMaxAge: 300000,
  dmCacheMaxSize: 10,
  dmCacheMaxAge: 100000
}
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [connect] Connected
[Tue Nov 23 2021 12:13:05 GMT+0100 (West Africa Standard Time)] INFO [login] Logging in hubot.bot
[Tue Nov 23 2021 12:13:06 GMT+0100 (West Africa Standard Time)] INFO [subscribe] Preparing subscription: stream-room-messages: __my_messages__
[Tue Nov 23 2021 12:13:06 GMT+0100 (West Africa Standard Time)] INFO [subscribe] Stream ready: 2
[Tue Nov 23 2021 12:13:06 GMT+0100 (West Africa Standard Time)] INFO [reactive] Listening for change events in collection stream-room-messages
[Tue Nov 23 2021 12:13:06 GMT+0100 (West Africa Standard Time)] INFO [joinRoom] Calling (async): ["ZgMPgTerjXmKyGzH4"]
```

### Test your Hubot Bot

To test if your bot has  successfully been connected, login to your server as a different user, go to the channel specified in the configuration of the bot and type this message.

```
@mybotuser what time is it
```

![](<../../.gitbook/assets/image (90) (1).png>)

The bot will reply and you will also see changes in the logs on your terminal.

```
[Tue Nov 23 2021 12:13:56 GMT+0100 (West Africa Standard Time)] INFO [received] Message in room ZgMPgTerjXmKyGzH4
[Tue Nov 23 2021 12:13:56 GMT+0100 (West Africa Standard Time)] INFO [received] Message Nyyg4oX7M7FQ6N6ka from rodriq
[Tue Nov 23 2021 12:13:56 GMT+0100 (West Africa Standard Time)] INFO Filters passed, will receive message
[Tue Nov 23 2021 12:14:04 GMT+0100 (West Africa Standard Time)] INFO [received] Message in room ZgMPgTerjXmKyGzH4
[Tue Nov 23 2021 12:14:04 GMT+0100 (West Africa Standard Time)] INFO [received] Message RPeaSjJThPNhZ7WSw from rodriq
[Tue Nov 23 2021 12:14:04 GMT+0100 (West Africa Standard Time)] INFO Filters passed, will receive message
[Tue Nov 23 2021 12:14:04 GMT+0100 (West Africa Standard Time)] INFO [sendMessage] Calling (async): [{"msg":"@rodriq It's 12:14 and 4 seconds","bot":{"i":"js.SDK"},"rid":"ZgMPgTerjXmKyGzH4"}];
```

Another command:

```
mybotuser rc version
```

![](../../.gitbook/assets/rc-version.png)

This message will also appear in the terminal window:

```
[Fri Sep 27 2019 23:40:20 GMT+0300 (Eastern European Summer Time)] INFO [received] Message in room GENERAL
i Sep 27 2019 23:40:20 GMT+0300 (Eastern European Summer Time)] INFO [received] Message AvnvCca3Do8PPfRCB from docsUser
[Fri Sep 27 2019 23:40:20 GMT+0300 (Eastern European Summer Time)] INFO Filters passed, will receive message
[Fri Sep 27 2019 23:40:21 GMT+0300 (Eastern European Summer Time)] INFO [sendMessage] Calling (async): [{"msg":"You're on Rocket.Chat 1.2.0-rc.0, using Hubot 3.3.2.","bot":{"i":"js.SDK"},"rid":"GENERAL"}]
[Fri Sep 27 2019 23:40:21 GMT+0300 (Eastern European Summer Time)] INFO [sendMessage] Calling (async): [{"msg":"Adapter version 2.0.0-development, using version 0.2.9 of the SDK.","bot":{"i":"js.SDK"},"rid":"GENERAL"}]
[Fri Sep 27 2019 23:40:21 GMT+0300 (Eastern European Summer Time)] INFO [received] Message in room GENERAL
```

### Run a Hubot Bot

#### Running in production

With the example above, you can run the bot in production using the following command:

```
bin/hubot -a rocketchat
```

There are executables for different environments that all run the Hubot binary:

* `bin/hubot` - for Linux/Unix
* `bin/hubot.cmd` - for Windows
* `Procfile` - for Heroku

Before running, make sure your production environment has the required environment variables for the adapter, url, user, name and pass. As an alternative, you can add them as command-line parameters, like `-a rocketchat`.

Environmental variables should be populated on the server before the launch (see [configuration](develop-a-hubot-bot.md#configuration)). The launcher will also install npm dependencies on every run, if booting in a fresh container (this isn't required when working locally).

See more information on deployment configurations [here](https://hubot.github.com/docs/deploying/).

## Advanced instructions

### Configuration

When running locally, [`dotenv`](https://www.npmjs.com/package/dotenv) is used to load configurations from the `.env` file. That makes it easier to set environment variables.

Please a full list of environmental variables here [Broken link](broken-reference "mention")

{% hint style="info" %}
Please pay attention that if `ROCKETCHAT_URL` is using `https://`, you **MUST** setup websocket pass-through on your reverse proxy (for example, NGINX) with a valid certificate (not self-signed). Directly accessing Rocket.Chat without a reverse proxy via `https://` is not possible.
{% endhint %}

### Adding scripts

Scripts can be added to the `./scripts` folder, or by installing node packages and listing their names in the `external-scripts.json` array. There is an example of each in this repo but neither is required.

### Checking example scripts

The boilerplate comes pre-packed with two scripts as demos for manual tests. In each of the following script, you can talk to a bot in a public channel by prefixing the bot's username or in direct messages without the bot's username.

* `what time is it` or `what's the time` - Tells you the current time
* `rc version` - Gives you version info about Rocket.Chat and Hubot (two messages)

## Deploy your Hubot Bot

### Deployment using Docker

* Clone the bot and navigate into it's directory by running

```
git clone https://github.com/RocketChat/hubot-rocketchat.git
cd hubot-rocketchat
```

* Next, start the docker container by running

```
docker run -it -e ROCKETCHAT_URL=<your rocketchat instance>:<port> \
    -e ROCKETCHAT_ROOM='' \
    -e LISTEN_ON_ALL_PUBLIC=true \
    -e RESPOND_TO_DM=true \
    -e ROCKETCHAT_USER=mybotuser \
    -e ROCKETCHAT_PASSWORD=mybotpassword \
    -e HUBOT_NAME=bot \
    -e EXTERNAL_SCRIPTS=hubot-help,hubot-diagnostics \
    rocketchat/hubot-rocketchat
```

{% hint style="warning" %}
The first time you run the docker container, the image needs to be pulled from the public docker registry, which takes some time. Subsequent runs are super fast.
{% endhint %}

On the container launch, hubot will try to connect to the Rocket.Chat instance and then will listen to messages in all public rooms:

```
[Sun Sep 29 2019 16:49:54 GMT+0000 (UTC)] INFO Starting Rocketchat adapter version 1.0.11...
[Sun Sep 29 2019 16:49:54 GMT+0000 (UTC)] INFO Once connected to rooms I will respond to the name: rocketbot
[Sun Sep 29 2019 16:49:54 GMT+0000 (UTC)] INFO I will also respond to my Rocket.Chat username as an alias: mybotuser
[Sun Sep 29 2019 16:49:54 GMT+0000 (UTC)] WARNING No services ROCKETCHAT_ROOM provided to Hubot, using
[Sun Sep 29 2019 16:49:54 GMT+0000 (UTC)] INFO Connecting To: <rocketchat_instance>
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Successfully connected!
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Logging In
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Successfully Logged In
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO rid:  []
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO All rooms joined.
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Preparing Meteor Subscriptions..
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Subscribing to Room: __my_messages__
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Successfully subscribed to messages
[Sun Sep 29 2019 16:49:55 GMT+0000 (UTC)] INFO Setting up reactive message list...
```

**3. talk to your bot**

On the server, login as a regular user (not the BOT user), go to `general` or any other room, and try the following command:

```
mybotuser time
```

You can also talk to the bot using its alias:

```
rocketbot time
```

Both commands result in the same output:

.

![](../../.gitbook/assets/docker-hubot-time.png)

{% hint style="info" %}
If you are not running Linux (i.e. if you are on a Mac or PC), you cannot use $PWD to mount the volumes. Instead, [read the _If you are using Boot2Docker..._ note](https://docs.docker.com/userguide/dockervolumes/) to determine the absolute path where you must place the git-cloned directory.
{% endhint %}

#### Adding scripts

To include your own scripts, you can use the following Docker command:

```
docker run -it -e ROCKETCHAT_URL=your rocketchat instance>:<port> \
    -e ROCKETCHAT_ROOM='' \
    -e LISTEN_ON_ALL_PUBLIC=true \
    -e RESPOND_TO_DM=true \
    -e ROCKETCHAT_USER=mybotuser \
    -e ROCKETCHAT_PASSWORD=mybotpassword \
    -e HUBOT_NAME=bot \
    -e EXTERNAL_SCRIPTS=hubot-help,hubot-diagnostics \
    -v $PWD/scripts:/home/hubot/scripts \
    rocketchat/hubot-rocketchat
```

### Deployment using Yeoman

[Yeoman generator](https://github.com/hubotio/generator-hubot) allows you to generate a Hubot bot using the Rocket.Chat adapter. Yeoman uses the latest versions of Hubot and Rocket.Chat adapter module, which enable asynchronous processing in ES6 Javascript, and introduce various bug fixes.

## Development for different versions of adapter

#### v2.x.x

**Standard**

In a Hubot instance once `hubot-rocketchat` is added by npm or yarn, you can replace the package with a development version directly:

* `cd node_modules` from the bot's project root
* `rm -rf hubot-rocketchat` to delete the published version
* `git clone git@github.com:RocketChat/hubot-rocketchat.git` to add dev version
* `cd hubot-rocketchat` move to dev path
* `npm install` install dependencies

**Linked**

Setting up a locally linked package is easier for continued development and/or using the same development version of the adapter in multiple bots.

* Change directory to your development adapter path
* `npm link` or `yarn link` to set the origin of the link
* Change directory to your bot's project root
* `npm link hubot-rocketchat` or `yarn link hubot-rocketchat` to create the link

#### v1.x.x and v0.x.x

**Docker-compose**

If you want to use docker-compose for this task, add this for v0.1.4 adapter (this must be inserted in your docker-compose.yml):

```
# hubot, the popular chatbot (add the bot user first and change the password before starting this image)
hubot:
image: rocketchat/hubot-rocketchat:v0.1.4
environment:
    - ROCKETCHAT_URL=your-rocket-chat-instance-ip:3000 (e.g. 192.168.2.240:3000)
    - ROCKETCHAT_ROOM=general
    - RESPOND_TO_DM=true
    - ROCKETCHAT_USER=username-of-your-bot
    - ROCKETCHAT_PASSWORD=yourpass
    - BOT_NAME=bot
    - GOOGLE_API_KEY=yourgoogleapikey
# you can add more scripts as you'd like here, they need to be installable by npm
    - EXTERNAL_SCRIPTS=hubot-help,hubot-seen,hubot-links,hubot-diagnostics,hubot-google,hubot-reddit,hubot-bofh,hubot-bookmark,hubot-shipit,hubot-maps
links:
    - rocketchat:rocketchat
# this is used to expose the hubot port for notifications on the host on port 3001, e.g. for hubot-jenkins-notifier
ports:
    - 3001:8080
```

If you want your bot to listen to all public rooms and all private rooms it is joined to, leave the env `ROCKETCHAT_ROOM` empty like in the example above and set the env `LISTEN_ON_ALL_PUBLIC=true`.

Please pay attention to some external scripts that are in the example above, as some of them need your Google-API-Key in the docker compose file.

## Version information and compatibility

The examples above use [Hubot](https://github.com/hubotio/hubot) v3 and [Rocketchat.Chat adapter](https://github.com/rocketchat/hubot-rocketchat) v2, using the new \[Rocket.Chat JS SDK]\[[sdk](https://github.com/rocketchat/Rocket.Chat.js.SDK) for Rocket.Chat instances 0.60.0 onward.

v2 contains major breaking changes. Starting with this version:

* CoffeeScript BOTs will no longer be supported, all new bot scripts should be written in NodeJS 8 compatible JavaScript
* Only [Hubot v3](https://github.com/hubotio/hubot/tree/v3) will be supported
* [Rocket.Chat Server version 0.63.0](https://github.com/RocketChat/Rocket.Chat/releases/tag/0.63.0) or higher is supported
* Yeoman generator support is discontinued, you should start your project with our [hubot v3 boilerplate](https://github.com/RocketChat/hubot-rocketchat-boilerplate)
* [NodeJS 8](https://nodejs.org) or later is required for operations
* The latest ES6 syntax in NodeJS 8, including the popular async-await, is fully supported

### Hubot versions

Versions of `hubot-rocketchat` prior to v2 are incompatible with Hubot v3

This bot is written in ES6 and intended to run on Node v8+. To run a bot on older versions of Node would require compilation with Babel to use the full ES6 feature set.

### Adapter versions

Older versions of the adapter (before v0.1.4) are incompatible with more recent versions of Rocket.Chat (v0.35+). Please report an issue, if you find specific version mismatch.

NOTE: releases between 0.35.0 and 0.37.1 are not recommended for hubot operations.

Rocket.Chat adapter v1 uses CoffeeScript, which makes extention of classes in JavaScript ES6 troublesome.

v1 versions of the adapter are only compatible with 0.37.1 and higher of Rocket.Chat Server. However, you should be able to continue using v1 adapter and CoffeeScript bots with the most up-to-date version of the server.

If you are writing CoffeeScript bots, you need Hubot v2.x and v1.x.x or v0.x.x of the adapter. Please see [instructions for v1.x.x and v0.x.x of the adapter](develop-a-hubot-bot.md#v1xx-and-v0xx).

## Additional information

For more examples on building and scripting your bot, please see [Hubot documentation](https://hubot.github.com/docs/).

## Contributions and discussions

Please see [our documentation on contributing](https://docs.rocket.chat/contributing/developing/), then [visit the issues](https://github.com/RocketChat/hubot-rocketchat-boilerplate/issues) to share your needs or ideas.

If you want to contribute to the development or improvement of this adapter, pull requests are welcome.

Feel free to join us in the [#hubot](https://open.rocket.chat/channel/hubot) channel to discuss hubot, and any scripts you might be working on.
