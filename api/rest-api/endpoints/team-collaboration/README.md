# Team Collaboration

## Assets

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | Set an asset image by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset) |
| `/api/v1/assets.unsetAsset` | Unset an asset by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset) |

## Auto Translate

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.getSupportedLanguages` | Get the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings` | Save some settings about auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings) |
| `/api/v1/autotranslate.translateMessage` | Translate the message. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage) |



## Banners

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/banners.getNew` | Get  | Link |
| `/api/v1/banners.dismiss` | Post | Link |

## Channels

These methods apply to public channels only. Use `groups.*` methods for private channels.

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/channels.addAll` | Adds all of the users on the server to a channel. | [Link](channels/addall.md) |
| `/api/v1/channels.addLeader` | Gives the role of Leader for a user in the current channel. | [Link](channels/addleader.md) |
| `/api/v1/channels.addModerator` | Gives the role of moderator to a user in a channel. | [Link](channels/addmoderator.md) |
| `/api/v1/channels.addOwner` | Gives the role of owner to a user in a channel. | [Link](channels/addowner.md) |
| `/api/v1/channels.anonymousread` | Gets the messages in public channels to an anonymous user | [Link](channels/anonymousread.md) |
| `/api/v1/channels.archive` | Archives a channel. | [Link](channels/archive.md) |
| `/api/v1/channels.close` | Removes a channel from a user's list of channels. | [Link](channels/close.md) |
| `/api/v1/channels.counters` | Gets channel counters. | [Link](channels/counters.md) |
| `/api/v1/channels.create` | Creates a new channel. | [Link](channels/create.md) |
| `/api/v1/channels.delete` | Removes a channel. | [Link](channels/delete.md) |
| `/api/v1/channels.getAllUserMentionsByChannel` | Gets all the mentions of a channel. | [Link](channels/getallusermentionsbychannel.md) |
| `/api/v1/channels.files` | Gets a list of files from a channel. | [Link](channels/files.md) |
| `/api/v1/channels.getIntegrations` | Gets the channel's integration. | [Link](channels/getintegrations.md) |
| `/api/v1/channels.history` | Retrieves the messages from a channel. | [Link](channels/history.md) |
| `/api/v1/channels.info` | Gets a channel's information. | [Link](channels/info.md) |
| `/api/v1/channels.invite` | Adds a user to a channel. | [Link](channels/invite.md) |
| `/api/v1/channels.join` | Joins yourself to a channel. | [Link](channels/join.md) |
| `/api/v1/channels.kick` | Removes a user from a channel. | [Link](channels/kick.md) |
| `/api/v1/channels.leave` | Removes the calling user from a channel. | [Link](channels/leave.md) |
| `/api/v1/channels.list` | Retrieves all of the channels from the server. | [Link](channels/list.md) |
| `/api/v1/channels.list.joined` | Gets only the channels the calling user has joined. | [Link](channels/list-joined.md) |
| `/api/v1/channels.members` | Retrieves all channel users. | [Link](channels/members.md) |
| `/api/v1/channels.messages` | Retrieves all channel messages. | [Link](channels/messages.md) |
| `/api/v1/channels.moderators` | List all moderators of a channel. | [Link](channels/moderators.md) |
| `/api/v1/channels.online` | List all online users of a channel. | [Link](channels/online.md) |
| `/api/v1/channels.open` | Adds the channel back to the user's list of channels. | [Link](channels/open.md) |
| `/api/v1/channels.removeleader` | Removes the role of Leader for a user in the current channel. | [Link](channels/removeleader.md) |
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
| `/api/v1/channels.setReadOnly` | Sets whether a channel is read only or not. | [Link](channels/setreadonly.md) |
| `/api/v1/channels.setTopic` | Sets a channel's topic. | [Link](channels/settopic.md) |
| `/api/v1/channels.setType` | Sets the type of room the channel should be. | [Link](channels/settype.md) |
| `/api/v1/channels.unarchive` | Unarchives a channel. | [Link](channels/unarchive.md) |

