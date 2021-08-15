# Team Collaboration Endpoints

## Assets

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | Set an asset image by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset) |
| `/api/v1/assets.unsetAsset` | Unset an asset by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset) |

## Auto Translate

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.getSupportedLanguages` | Get the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings` | Save some settings about auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings) |
| `/api/v1/autotranslate.translateMessage` | Translate the message. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage) |



## Banners

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/banners.getNew` | Get  | Link |
| `/api/v1/banners.dismiss` | Post | Link |

## Channels

These methods apply to public channels only. Use `groups.*` methods for private channels.

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/channels.addAll` | Adds all of the users on the server to a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addall) |
| `/api/v1/channels.addLeader` | Gives the role of Leader for a user in the current channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addleader) |
| `/api/v1/channels.addModerator` | Gives the role of moderator to a user in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addmoderator) |
| `/api/v1/channels.addOwner` | Gives the role of owner to a user in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addowner) |
| `/api/v1/channels.anonymousread` | Gets the messages in public channels to an anonymous user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/anonymousread) |
| `/api/v1/channels.archive` | Archives a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/archive) |
| `/api/v1/channels.close` | Removes a channel from a user's list of channels. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/close) |
| `/api/v1/channels.counters` | Gets channel counters. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/counters) |
| `/api/v1/channels.create` | Creates a new channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/create) |
| `/api/v1/channels.delete` | Removes a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/delete) |
| `/api/v1/channels.getAllUserMentionsByChannel` | Gets all the mentions of a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/getallusermentionsbychannel) |
| `/api/v1/channels.files` | Gets a list of files from a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/files) |
| `/api/v1/channels.getIntegrations` | Gets the channel's integration. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/getintegrations) |
| `/api/v1/channels.history` | Retrieves the messages from a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/history) |
| `/api/v1/channels.info` | Gets a channel's information. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/info) |
| `/api/v1/channels.invite` | Adds a user to a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/invite) |
| `/api/v1/channels.join` | Joins yourself to a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/join) |
| `/api/v1/channels.kick` | Removes a user from a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/kick) |
| `/api/v1/channels.leave` | Removes the calling user from a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/leave) |
| `/api/v1/channels.list` | Retrieves all of the channels from the server. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/list) |
| `/api/v1/channels.list.joined` | Gets only the channels the calling user has joined. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/list-joined) |
| `/api/v1/channels.members` | Retrieves all channel users. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/members) |
| `/api/v1/channels.messages` | Retrieves all channel messages. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/messages) |
| `/api/v1/channels.moderators` | List all moderators of a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/moderators) |
| `/api/v1/channels.online` | List all online users of a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/online) |
| `/api/v1/channels.open` | Adds the channel back to the user's list of channels. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/open) |
| `/api/v1/channels.removeleader` | Removes the role of Leader for a user in the current channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/removeleader) |
| `/api/v1/channels.removeModerator` | Removes the role of moderator from a user in a channel. | [Link](channels/removemoderator.md) |
| `/api/v1/channels.removeOwner` | Removes the role of owner from a user in a channel. | [Link](channels/removeowner.md) |
| `/api/v1/channels.rename` | Changes a channel's name. | [Link](channels/rename.md) |
| `/api/v1/channels.roles` | Gets the user's roles in the channel. | [Link](channels/roles.md) |
| `/api/v1/channels.setAnnouncement` | Sets a channel's announcement. | [Link](channels/setannouncement.md) |
| `/api/v1/channels.setCustomFields` | Sets a channel's custom fields. | [Link](channels/setcustomfields.md) |
| `/api/v1/channels.setDefault` | Sets a channel's default status. | [Link](channels/setdefault.md) |
| `/api/v1/channels.setDescription` | Sets a channel's description. | [Link](channels/setdescription.md) |
| `/api/v1/channels.setJoinCode` | Sets the channel's code required to join it. | [Link](channels/setjoincode.md) |
| `/api/v1/channels.setPurpose` | Sets a channel's description. | [Link](channels/setpurpose.md) |
| `/api/v1/channels.setReadOnly` | Sets whether a channel is read-only or not. | [Link](channels/setreadonly.md) |
| `/api/v1/channels.setTopic` | Sets a channel's topic. | [Link](channels/settopic.md) |
| `/api/v1/channels.setType` | Sets the type of room the channel should be. | [Link](channels/settype.md) |
| `/api/v1/channels.unarchive` | Unarchives a channel. | [Link](channels/unarchive.md) |
| channels.convertToTeam | post |  |

## Chat

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/chat.delete` | Deletes an existing chat message. | [Link](chat/delete.md) |
| `/api/v1/chat.followMessage` | Follows an existing chat message. | [Link](chat/followmessage.md) |
| `/api/v1/chat.getDeletedMessages` | Retrieves the deleted messages from a specific date. | [Link](chat/getdeletedmessages.md) |
| `/api/v1/chat.getDiscussions` | Retrieves the discussions of a room. | [Link](chat/getdiscussions.md) |
| `/api/v1/chat.getMentionedMessages` | Retrieves the mentioned messages. | [Link](chat/getmentionedmessages.md) |
| `/api/v1/chat.getMessage` | Retrieves a single chat message. | [Link](chat/getmessage.md) |
| `/api/v1/chat.getMessageReadReceipts` | Retrieves message read receipts. | [Link](chat/getmessagereadreceipts.md) |
| `/api/v1/chat.getPinnedMessages` | Retrieve pinned messages from a room. | [Link](chat/getpinnedmessages.md) |
| `/api/v1/chat.getSnippetedMessages` | Retrieves snippeted messages. | [Link](chat/getsnippetedmessages.md) |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippeted message by id. | [Link](chat/getsnippetedmessagebyid.md) |
| `/api/v1/chat.getStarredMessages` | Retrieves the starred messages. | [Link](chat/getstarredmessages.md) |
| `/api/v1/chat.getThreadMessages` | Retrieves thread's messages. | [Link](chat/getthreadmessages.md) |
| `/api/v1/chat.getThreadsList` | Retrieves channel's threads. | [Link](chat/getthreadslist.md) |
| `/api/v1/chat.ignoreUser` | Ignores an user from a chat. | [Link](chat/ignoreuser.md) |
| `/api/v1/chat.pinMessage` | Pins a chat message to the message's channel. | [Link](chat/pinmessage.md) |
| `/api/v1/chat.postMessage` | Posts a new chat message. | [Link](chat/postmessage.md) |
| `/api/v1/chat.react` | Sets/unsets the user's reaction to an existing chat message. | [Link](chat/chat-message-reactions.md) |
| `/api/v1/chat.reportMessage` | Reports a message. | [Link](chat/reportmessage.md) |
| `/api/v1/chat.search` | Search for messages in a channel. | [Link](chat/search-message.md) |
| `/api/v1/chat.starMessage` | Stars a chat message for the authenticated user. | [Link](chat/starmessage.md) |
| `/api/v1/chat.sendMessage` | Send a new chat message. | [Link](chat/sendmessage.md) |
| `/api/v1/chat.syncThreadMessages` | Retrieves synced thread's messages. | [Link](chat/syncthreadmessages.md) |
| `/api/v1/chat.syncThreadsList` | Retrieves thread's synced channel threads. | [Link](chat/syncthreadslist.md) |
| `/api/v1/chat.unfollowMessage` | Unfollows an existing chat message. | [Link](chat/unfollowmessage.md) |
| `/api/v1/chat.unPinMessage` | Removes the pinned status of the provided chat message. | [Link](chat/unpinmessage.md) |
| `/api/v1/chat.unStarMessage` | Removes the star on the chat message for the authenticated user. | [Link](chat/unstarmessage.md) |
| `/api/v1/chat.update` | Updates the text of the chat message. | [Link](chat/message-update.md) |
| chat.syncMessages | get |  |

## Cloud

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/`cloud.manualRegister | Post | Link |

## Commands

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/commands.get` | Get the specification of the slash command. | [Link](commands/get-lash-commands.md) |
| `/api/v1/commands.list` | Lists all available slash commands. | [Link](commands/list.md) |
| `/api/v1/commands.run` | Execute a slash command in the specified room. | [Link](commands/run.md) |
| `/api/v1/commands.preview` | Gets the preview data for the command and executes the preview item. | [Link](commands/preview.md) |

## Custom Sounds

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | ​[Link](https://app.gitbook.com/@rocket-chat/s/rocket-chat-developer/~/drafts/-MgSmy428hAP1znS6g3V/api/rest-api/endpoints/team-collaboration/custom-sounds/list)​ |

## Custom User Status

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-user-status.list` | Lists all available custom user's status. | [Link](custom-user-status/list.md) |
| custom-user-status.create | post |  |
| custom-user-status.delete | post |  |
| custom-user-status.update | post |  |



## DNS

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| dns.resolve.srv | get | Link |
| dns.resolve.txt | post | Link |

## E2E Endpoints



| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| e2e.fetchMyKeys | get | Link |
| e2e.getUsersOfRoomWithoutKey | post | Link |
| e2e.setRoomKeyID | post |  |
| e2e.setUserPublicAndPrivateKeys | post |  |
| e2e.updateGroupKey | post |  |

