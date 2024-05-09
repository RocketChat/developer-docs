# Bots Development Environment Setup

### Requirements

Developing bots on RocketChat requires you to get and customize our boilerplate code. To do that, you need to have the following on your machine.

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)

### Bot Configuration

Regardless of bot type, the Rocket.Chat SDK requires you to create a configuration with some variables for your environment. This configuration can be stored in a `.env` file, for local development, for example. In production, they would need to be set on server startup.

### Bots Environmental variables

The following is a list of all the environmental variables you can use in your project.

{% hint style="info" %}
**Variables marked with an asterisk (`*`) are mandatory.**
{% endhint %}

| Environment Variable               | Description                                                                                                                                                                                                                                                                                                    |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ROCKETCHAT_URL` \*                | URL of the Rocket.Chat instance to connect to. Can be specified as `host:port`, `http://host:port` or `https://host:port`.                                                                                                                                                                                     |
| `ROCKETCHAT_USE_SSL`               | Force bot to connect with SSL. If unset, it will try and detect from URL protocol.                                                                                                                                                                                                                             |
| `ROCKETCHAT_AUTH`                  | Authorization method for a bot. Default: `password`. Set to `ldap` to enable LDAP login for bot users.                                                                                                                                                                                                         |
| `ROCKETCHAT_USER` \*               | The bot's username (account name users will summon the bot with). Must be registered on your Rocket.Chat server and granted `bot` role.                                                                                                                                                                        |
| `ROCKETCHAT_PASSWORD` \*           | The bot user's password.                                                                                                                                                                                                                                                                                       |
| `ROCKETCHAT_ROOM`                  | Stream callbacks receive messages from the listed channel name/s. Default: `GENERAL`. Accepts a comma separated list. Allows the bot to listen and respond to messages _from all newly created private groups_ where the bot's user has been added as a member. Should be empty if `LISTEN_ON_ALL_PUBLIC=true` |
| **Responding to channels and DMS** |                                                                                                                                                                                                                                                                                                                |
| `RESPOND_TO_LIVECHAT`              | Stream callbacks receive messages from Livechat (true/false). Default: `false`.                                                                                                                                                                                                                                |
| `RESPOND_TO_DM`                    | Stream callbacks receive DMs with bot (true/false). Default: `false`.                                                                                                                                                                                                                                          |
| `RESPOND_TO_EDITED`                | Stream callbacks receive edited messages (true/false). Default: `false`.                                                                                                                                                                                                                                       |
| **SDK Development**                |                                                                                                                                                                                                                                                                                                                |
| `ROOM_CACHE_SIZE`                  | Size of cache (LRU) for room (ID or name) lookups.                                                                                                                                                                                                                                                             |
| `ROOM_CACHE_MAX_AGE`               | Max age of cache for room lookups.                                                                                                                                                                                                                                                                             |
| `DM_ROOM_CACHE_SIZE`               | Size of cache for Direct Message room lookups.                                                                                                                                                                                                                                                                 |
| `DM_ROOM_CACHE_MAX_AGE`            | Max age of cache for DM lookups.                                                                                                                                                                                                                                                                               |
| `INTEGRATION_ID`                   | ID applied to message object to integration source. Default: `js.SDK`                                                                                                                                                                                                                                          |
| `ADMIN_USERNAME`                   | Admin user name for API calls used in SDK tests.                                                                                                                                                                                                                                                               |
| `ADMIN_PASS`                       | Admin user password for API calls used in SDK tests.                                                                                                                                                                                                                                                           |
| **Hubot Specific**                 |                                                                                                                                                                                                                                                                                                                |
| `HUBOT_NAME`                       | Name of the bot. Hubot listeners can respond to this.                                                                                                                                                                                                                                                          |
| `HUBOT_ALIAS`                      | Another name to respond to. If unset, the adapter sets the `ROCKETCHAT_USER` as an alias, to ensure bots respond when addressed using their username.                                                                                                                                                          |
| `EXTERNAL_SCRIPTS`                 | Hubot scripts to require as NPM modules. Used only in some Docker instances.                                                                                                                                                                                                                                   |
| `HUBOT_LOG_LEVEL`                  | `debug`, `info`, `warning` or `error`. Default: `info`.                                                                                                                                                                                                                                                        |                                                                                                                                                     |

### Common Set of Variables

The common set for the majority of bots is to listen and respond to direct messages and all new public channels and private groups:

* `RESPOND_TO_DM=true`
* `ROCKETCHAT_ROOM=''`

{% hint style="info" %}
Note that you must add the bot's user as a member of the new private group(s) before it will respond.
{% endhint %}
