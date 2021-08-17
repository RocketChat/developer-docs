# REST API

The REST API allows you to control and extend Rocket.Chat with ease.

> **This API is a work in progress, so feel free to test, ask us questions, and submit Pull Requests!**

If you are an end-user and not a dev or a tester, [create a New Feature Request](https://forums.rocket.chat/c/feature-requests) to request new APIs -- and consider [making a donation](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZL94ZE6LGVUSN) to the project.

> All API calls in the documentation are made using `curl`. However, you are free to use Java / Python / PHP / Golang / Ruby / Swift / Objective-C / Rust / Scala / C\# or any other programming languages.

## Production Security Concerns

When calling a production Rocket.Chat server, ensure it is running via HTTPS and has a valid SSL Certificate. The login method requires you to post your username and password in plaintext, which is why we highly suggest only calling the REST login API over HTTPS. Also, few things to note:

* Only call via HTTPS
* Implement a timed authorization token expiration strategy
* Ensure the calling user only has permissions for what they are calling and no more

### Miscellaneous Information

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/info` | Information about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/info.md) |
| `/api/v1/directory` | Search by all users and channels available on server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/directory.md) |
| `/api/v1/shield.svg` | Gets the shield svg\(badge\) to add in your website. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/shield-svg.md) |
| `/api/v1/spotlight` | Searches for users or rooms that are visible to the user. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/spotlight.md) |
| `/api/v1/statistics` | Statistics about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/statistics.md) |
| `/api/v1/statistics.list` | Selectable statistics about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous-endpoints/statistics-list.md) |
| `/api/v1/instances.get` | Gets all running instances. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/miscellaneous/instances-get.md) |

### Assets

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | Set an asset image by name. | [Link](endpoints/team-collaboration-endpoints/assets-endpoints/setasset.md) |
| `/api/v1/assets.unsetAsset` | Unset an asset by name | [Link](endpoints/team-collaboration-endpoints/assets-endpoints/unset-asset.md) |

### AutoTranslate

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.getSupportedLanguages` | Get the supported languages by the autotranslate. | [Link](endpoints/team-collaboration-endpoints/auto-translate-endpoints/getsupportedlanguages.md) |
| `/api/v1/autotranslate.saveSettings` | Save some settings about autotranslate. | [Link](endpoints/team-collaboration-endpoints/auto-translate-endpoints/savesettings.md) |
| `/api/v1/autotranslate.translateMessage` | Translate the message. | [Link](endpoints/team-collaboration-endpoints/auto-translate-endpoints/translatemessage.md) |

### Authentication

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/login` | Authenticate with the REST API. | [Link](endpoints/team-collaboration-endpoints/others/authentication/login.md) |
| `/api/v1/login` | Authenticate with google. | [Link](endpoints/team-collaboration-endpoints/others/authentication/google.md) |
| `/api/v1/login` | Authenticate with facebook. | [Link](endpoints/team-collaboration-endpoints/others/authentication/facebook.md) |
| `/api/v1/login` | Authenticate with twitter. | [Link](endpoints/team-collaboration-endpoints/others/authentication/twitter.md) |
| `/api/v1/logout` | Invalidate your REST API authentication token. | [Link](endpoints/team-collaboration-endpoints/others/authentication/logout.md) |
| `/api/v1/me` | Displays information about the authenticated user. | [Link](endpoints/team-collaboration-endpoints/others/authentication/me.md) |

### Users

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/users.presence` | Gets all connected users presence. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/presence.md) |
| `/api/v1/users.create` | Create a new user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/create-user.md) |
| `/api/v1/users.createToken` | Create a user authentication token. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/createtoken.md) |
| `/api/v1/users.deactivateIdle` | Deactivate idle users. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/deactivateidle.md) |
| `/api/v1/users.delete` | Deletes an existing user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/delete.md) |
| `/api/v1/users.deleteOwnAccount` | Deletes your own user account. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/deleteownaccount.md) |
| `/api/v1/users.forgotPassword` | Send email to reset your password. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/forgotpassword.md) |
| `/api/v1/users.generatePersonalAccessToken` | Generate Personal Access Token. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/generatepersonalaccesstoken.md) |
| `/api/v1/users.getAvatar` | Gets the URL for a user's avatar. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/getavatar.md) |
| `/api/v1/users.getPersonalAccessTokens` | Gets the user's personal access tokens. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/getpersonalaccesstokens.md) |
| `/api/v1/users.getPreferences` | Gets all preferences of user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/get-preferences.md) |
| `/api/v1/users.getPresence` | Gets the online presence of a user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/getpresence.md) |
| `/api/v1/users.getStatus` | Gets the user's status. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/getstatus.md) |
| `/api/v1/users.getUsernameSuggestion` | Gets a suggestion a new username to user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/getusernamesuggestion.md) |
| `/api/v1/users.info` | Gets a user's information, limited to the caller's permissions. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/info.md) |
| `/api/v1/users.list` | All of the users and their information, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/list.md) |
| `/api/v1/users.regeneratePersonalAccessToken` | Regenerate a user personal access token. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/regeneratepersonalaccesstoken.md) |
| `/api/v1/users.register` | Register a new user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/register.md) |
| `/api/v1/users.removeOtherTokens` | Remove all other user tokens | [Link](endpoints/team-collaboration-endpoints/users-endpoints/removeothertokens.md) |
| `/api/v1/users.removePersonalAccessToken` | Remove a personal access token. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/removepersonalaccesstoken.md) |
| `/api/v1/users.requestDataDownload` | Request users download data. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/requestdatadownload.md) |
| `/api/v1/users.resetAvatar` | Reset a user's avatar | [Link](endpoints/team-collaboration-endpoints/users-endpoints/resetavatar.md) |
| `/api/v1/users.setAvatar` | Set a user's avatar | [Link](endpoints/team-collaboration-endpoints/users-endpoints/setavatar.md) |
| `/api/v1/users.setPreferences` | Set user's preferences | [Link](endpoints/team-collaboration-endpoints/users-endpoints/set-preferences.md) |
| `/api/v1/users.setStatus` | Set the user's status | [Link](endpoints/team-collaboration-endpoints/users-endpoints/setstatus.md) |
| `/api/v1/users.setActiveStatus` | Set a user's active status. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/setactivestatus.md) |
| `/api/v1/users.update` | Update an existing user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/update.md) |
| `/api/v1/users.updateOwnBasicInfo` | Update basic information of own user. | [Link](endpoints/team-collaboration-endpoints/users-endpoints/updateownbasicinfo.md) |

### Channels

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/channels.addAll` | Adds all of the users on the server to a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/addall.md) |
| `/api/v1/channels.addLeader` | Gives the role of Leader for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/addleader.md) |
| `/api/v1/channels.addOwner` | Gives the role of owner for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/addowner.md) |
| `/api/v1/channels.anonymousread` | Gets the messages in public channels to an anonymous user | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/anonymousread.md) |
| `/api/v1/channels.archive` | Archives a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/archive.md) |
| `/api/v1/channels.close` | Removes a channel from a user's list of channels. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/close.md) |
| `/api/v1/channels.counters` | Gets channel counters. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/counters.md) |
| `/api/v1/channels.create` | Creates a new channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/create.md) |
| `/api/v1/channels.delete` | Removes a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/delete.md) |
| `/api/v1/channels.files` | Gets a list of files from a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/files.md) |
| `/api/v1/channels.getAllUserMentionsByChannel` | Gets all the mentions of a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/getallusermentionsbychannel.md) |
| `/api/v1/channels.getIntegrations` | Gets the channel's integration. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/getintegrations.md) |
| `/api/v1/channels.history` | Retrieves the messages from a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/history.md) |
| `/api/v1/channels.info` | Gets a channel's information. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/info.md) |
| `/api/v1/channels.invite` | Adds a user to a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/invite.md) |
| `/api/v1/channels.join` | Joins yourself to a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/join.md) |
| `/api/v1/channels.kick` | Removes a user from a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/kick.md) |
| `/api/v1/channels.leave` | Removes the calling user from a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/leave.md) |
| `/api/v1/channels.list` | Retrieves all of the channels from the server. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/list.md) |
| `/api/v1/channels.list.joined` | Gets only the channels the calling user has joined. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/list-joined.md) |
| `/api/v1/channels.members` | Retrieves all channel users. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/members.md) |
| `/api/v1/channels.messages` | Retrieves all channel messages. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/messages.md) |
| `/api/v1/channels.moderators` | List all moderators of a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/moderators.md) |
| `/api/v1/channels.online` | List all online users of a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/online.md) |
| `/api/v1/channels.open` | Adds the channel back to the user's list of channels. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/open.md) |
| `/api/v1/channels.removeleader` | Removes the role of Leader for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/removeleader.md) |
| `/api/v1/channels.rename` | Changes a channel's name. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/rename.md) |
| `/api/v1/channels.roles` | Gets the user's roles in the channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/roles.md) |
| `/api/v1/channels.setCustomFields` | Sets a channel's custom fields. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setcustomfields.md) |
| `/api/v1/channels.setAnnouncement` | Sets a channel's announcement. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setannouncement.md) |
| `/api/v1/channels.setDefault` | Sets whether a channel is a default channel or not. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setdefault.md) |
| `/api/v1/channels.setDescription` | Sets a channel's description. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setdescription.md) |
| `/api/v1/channels.setJoinCode` | Sets the channel's code required to join it. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setjoincode.md) |
| `/api/v1/channels.setPurpose` | Sets a channel's description. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setpurpose.md) |
| `/api/v1/channels.setReadOnly` | Sets whether a channel is read only or not. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/setreadonly.md) |
| `/api/v1/channels.setTopic` | Sets a channel's topic. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/settopic.md) |
| `/api/v1/channels.setType` | Sets the type of room the channel should be. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/settype.md) |
| `/api/v1/channels.unarchive` | Unarchives a channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/unarchive.md) |
| `/api/v1/channels.addOwner` | Gives the role of owner for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/addowner.md) |
| `/api/v1/channels.removeOwner` | Removes the role of owner from a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels-endpoints/removeowner.md) |

### Groups

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/groups.archive` | Archives a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/archive.md) |
| `/api/v1/groups.addLeader` | Gives the role of Leader for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/addleader.md) |
| `/api/v1/groups.close` | Removes a private group from the list of groups. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/close.md) |
| `/api/v1/groups.counters` | Gets group counters. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/counters.md) |
| `/api/v1/groups.create` | Creates a new private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/create.md) |
| `/api/v1/groups.delete` | Removes a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/delete.md) |
| `/api/v1/groups.files` | Gets a list of files from a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/files.md) |
| `/api/v1/groups.history` | Retrieves the messages from a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/history.md) |
| `/api/v1/groups.info` | Gets the information about a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/info.md) |
| `/api/v1/groups.invite` | Adds a user to the private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/invite.md) |
| `/api/v1/groups.kick` | Removes a user from a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/kick.md) |
| `/api/v1/groups.leave` | Removes the calling user from the private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/leave.md) |
| `/api/v1/groups.list` | List the private groups the caller is part of. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/list.md) |
| `/api/v1/groups.listAll` | List all the private groups. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/listall.md) |
| `/api/v1/groups.members` | Gets the users of participants of a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/members.md) |
| `/api/v1/groups.messages` | Retrieves all group messages. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/messages.md) |
| `/api/v1/groups.moderators` | List all moderators of a group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/moderators.md) |
| `/api/v1/groups.online` | List all online users of a group. | [Link](https://github.com/RocketChat/docs/tree/aeb4dd8de5017b7cd9c9d9367a0e2155f911ba5a/api/rest-api/methods/groups/online.md) |
| `/api/v1/groups.open` | Adds the private group back to the list of groups. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/open.md) |
| `/api/v1/groups.removeLeader` | Removes the role of Leader for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/removeleader.md) |
| `/api/v1/groups.rename` | Changes the name of the private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/rename.md) |
| `/api/v1/groups.roles` | Gets the user's roles in the private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/roles.md) |
| `/api/v1/groups.setAnnouncement` | Sets a group's announcement. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/setannouncement.md) |
| `/api/v1/groups.setCustomFields` | Sets private group's custom fields. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/setcustomfields.md) |
| `/api/v1/groups.setDescription` | Sets a private group's description. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/setdescription.md) |
| `/api/v1/groups.setPurpose` | Sets a private group's description. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/setpurpose.md) |
| `/api/v1/groups.setReadOnly` | Sets whether the room is read only or not. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/setreadonly.md) |
| `/api/v1/groups.setTopic` | Sets a private group's topic. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/settopic.md) |
| `/api/v1/groups.setType` | Sets the type of room this group will be. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/settype.md) |
| `/api/v1/groups.unarchive` | Unarchives a private group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/unarchive.md) |
| `/api/v1/groups.addOwner` | Gives the role of owner for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/addowner.md) |
| `/api/v1/groups.removeOwner` | Removes the role of owner from a user in the current Group. | [Link](endpoints/team-collaboration-endpoints/groups-endpoints/removeowner.md) |

### Chat

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/chat.delete` | Deletes an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/delete.md) |
| `/api/v1/chat.followMessage` | Follows an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/followmessage.md) |
| `/api/v1/chat.getDeletedMessages` | Retrieves the deleted messages since specific date. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getdeletedmessages.md) |
| `/api/v1/chat.getDiscussions` | Retrieves the discussions messages of a room. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getdiscussions.md) |
| `/api/v1/chat.getMentionedMessages` | Retrieves mentioned messages. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getmentionedmessages.md) |
| `/api/v1/chat.getMessage` | Retrieves a single chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getmessage.md) |
| `/api/v1/chat.getMessageReadReceipts` | Retrieves message read receipts. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getmessagereadreceipts.md) |
| `/api/v1/chat.getPinnedMessages` | Retrieve pinned messages from a room. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getpinnedmessages.md) |
| `/api/v1/chat.getSnippetedMessages` | Retrieves snippeted messages. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getsnippetedmessages.md) |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippeted message by id. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getsnippetedmessagebyid.md) |
| `/api/v1/chat.getStarredMessages` | Retrieves starred messages. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getstarredmessages.md) |
| `/api/v1/chat.getThreadMessages` | Retrieves thread's messages. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getthreadmessages.md) |
| `/api/v1/chat.getThreadsList` | Retrieves channel's threads. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/getthreadslist.md) |
| `/api/v1/chat.ignoreUser` | Ignores an user from a chat. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/ignoreuser.md) |
| `/api/v1/chat.pinMessage` | Pins a chat message to the message's channel. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/pinmessage.md) |
| `/api/v1/chat.postMessage` | Posts a new chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/postmessage.md) |
| `/api/v1/chat.react` | Sets/unsets the user's reaction to an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/chat-message-reactions.md) |
| `/api/v1/chat.reportMessage` | Reports a message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/reportmessage.md) |
| `/api/v1/chat.search` | Search for messages in a channel. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/search-message.md) |
| `/api/v1/chat.starMessage` | Stars a chat message for the authenticated user. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/starmessage.md) |
| `/api/v1/chat.sendMessage` | Send new chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/sendmessage.md) |
| `/api/v1/chat.syncThreadMessages` | Retrieves synced thread's messages. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/syncthreadmessages.md) |
| `/api/v1/chat.syncThreadsList` | Retrieves thread's synced channel threads. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/syncthreadslist.md) |
| `/api/v1/chat.unfollowMessage` | Unfollows an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/unfollowmessage.md) |
| `/api/v1/chat.unPinMessage` | Removes the pinned status of the provided chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/unpinmessage.md) |
| `/api/v1/chat.unStarMessage` | Removes the star on the chat message for the authenticated user. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/unstarmessage.md) |
| `/api/v1/chat.update` | Updates the text of the chat message. | [Link](endpoints/team-collaboration-endpoints/chat-endpoints/message-update.md) |

### Custom Sounds

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | [Link](endpoints/team-collaboration-endpoints/custom-sounds-endpoints/custom-sounds-list.md) |

### IM

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/im.close` | Removes a direct message from the list of direct messages. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/close.md) |
| `/api/v1/im.counters` | Gets counters of direct messages. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/counters.md) |
| `/api/v1/im.create` | Create a direct message session with another user. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/create.md) |
| `/api/v1/im.history` | Retrieves the messages from a direct message. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/history.md) |
| `/api/v1/im.files` | Retrieves a list of files from a direct message. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/files.md) |
| `/api/v1/im.members` | Retrieves the users of participants of a direct message. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/members.md) |
| `/api/v1/im.messages` | Retrieves the messages from specific direct message. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/messages.md) |
| `/api/v1/im.messages.others` | Retrieves the messages from any direct message in the server. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/messages-others.md) |
| `/api/v1/im.list` | List the direct messages the caller is part of. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/list.md) |
| `/api/v1/im.list.everyone` | List all direct message the caller in the server. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/list-everyone.md) |
| `/api/v1/im.open` | Adds the direct message back to the list of direct messages. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/open.md) |
| `/api/v1/im.setTopic` | Sets a direct message topic. | [Link](endpoints/team-collaboration-endpoints/im-endpoints/settopic.md) |

### Integrations

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/integrations.create` | Creates an integration. | [Link](endpoints/team-collaboration-endpoints/integration-endpoints/create.md) |
| `/api/v1/integrations.get` | Gets an integration. | [Link](endpoints/team-collaboration-endpoints/integration-endpoints/get.md) |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](endpoints/team-collaboration-endpoints/integration-endpoints/history.md) |
| `/api/v1/integrations.list` | Lists all of the integrations. | [Link](endpoints/team-collaboration-endpoints/integration-endpoints/list.md) |
| `/api/v1/integrations.remove` | Removes an integration. | [Link](endpoints/team-collaboration-endpoints/integration-endpoints/remove.md) |

### Invites

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/findOrCreateInvite` | Created a new Invite or returns an existing one with the same parameters. | [Link](endpoints/team-collaboration-endpoints/invite-endpoints/findorcreateinvite.md) |
| `/api/v1/listInvites` | Lists all of the invite tokens. | [Link](endpoints/team-collaboration-endpoints/invite-endpoints/listinvites.md) |
| `/api/v1/removeInvite` | Removes an invite. | [Link](endpoints/team-collaboration-endpoints/invite-endpoints/removeinvite.md) |
| `/api/v1/useInviteToken` | Report to the server that an invite token was used. | [Link](endpoints/team-collaboration-endpoints/invite-endpoints/useinvitetoken.md) |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid. | [Link](endpoints/team-collaboration-endpoints/invite-endpoints/validateinvitetoken.md) |

### Livechat

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.list` | Retrieves a list of open inquiries. | [Link](endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list.md#inquiries-list) |
| `/api/v1/livechat/inquiries.take` | Take an open inquiry. | [Link](endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list.md#livechat-take-inquiry) |
| `/api/v1/livechat/rooms` | Retrieves a list of livechat rooms. | [Link](endpoints/omnichannel/omnichannel-endpoints/rooms/) |

### OAuthApps

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/oauth-apps.get` | Retrieves an OAuth App by id or client id. | [Link](endpoints/team-collaboration-endpoints/oauthapps-endpoints/get.md) |
| `/api/v1/oauth-apps.list` | Retrieves a list of OAuth Apps. | [Link](endpoints/team-collaboration-endpoints/oauthapps-endpoints/list.md) |

### Permissions

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](endpoints/team-collaboration-endpoints/permissions-endpoints/listall.md) |
| `/api/v1/permissions.update` | Edits permissions on the server. | [Link](endpoints/team-collaboration-endpoints/permissions-endpoints/update.md) |

### Roles

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/roles.create` | Create a new role in the system. | [Link](endpoints/team-collaboration-endpoints/roles-endpoints/create.md) |
| `/api/v1/roles.list` | Gets all the roles in the system. | [Link](endpoints/team-collaboration-endpoints/roles-endpoints/list.md) |
| `/api/v1/roles.sync` | Gets all the roles in the system which are updated after a given date. | [Link](endpoints/team-collaboration-endpoints/roles-endpoints/sync.md) |
| `/api/v1/roles.addUserToRole` | Assign a role to an user. | [Link](endpoints/team-collaboration-endpoints/roles-endpoints/addusertorole.md) |
| `/api/v1/roles.getUsersInRole` | Gets the users that belongs to a role. | [Link](endpoints/team-collaboration-endpoints/roles-endpoints/getusersinrole.md) |
| `/api/v1/roles.update` | Update an existing role in the system. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/update.md) |
| `/api/v1/roles.delete` | Delete a role. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/delete.md) |

### Push Token

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/push.token` | `POST` | Saves push token. | [Link](endpoints/team-collaboration-endpoints/push-token-endpoints/push-token.md) |
| `/api/v1/push.token` | `DELETE` | Removes push token. | [Link](endpoints/team-collaboration-endpoints/push-token-endpoints/deletepushtoken.md) |

### Rooms

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/rooms.adminRooms` | Retrieve all rooms \(requires special permission\). | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/adminrooms.md) |
| `/api/v1/rooms.cleanHistory` | Cleans up a room's history, requires special permission. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/cleanhistory.md) |
| `/api/v1/rooms.createDiscussion` | Creates a new discussion. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/creatediscussion.md) |
| `/api/v1/rooms.favorite` | Favorite/Unfavorite room. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/favorite.md) |
| `/api/v1/rooms.get` | Gets rooms. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/get.md) |
| `/api/v1/rooms.getDiscussions` | Gets room's discussions. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/getdiscussions.md) |
| `/api/v1/rooms.info` | Gets info from a room. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/info.md) |
| `/api/v1/rooms.leave` | Leaves a room. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/leave.md) |
| `/api/v1/rooms.saveNotification` | Sets the notifications settings of specific channel. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/savenotification.md) |
| `/api/v1/rooms.upload/:rid` | Upload a message with attached file. | [Link](endpoints/team-collaboration-endpoints/rooms-endpoints/upload.md) |

### Teams

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/teams.addMembers` | Adds users to the team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/add-members.md) |
| `/api/v1/teams.addRooms` | Adds rooms to the team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/add-rooms.md) |
| `/api/v1/teams.autocomplete` | Lists the teams whose names match a given pattern. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/autocomplete.md) |
| `/api/v1/teams.create` | Creates a new team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/create.md) |
| `/api/v1/teams.delete` | Removes a team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/delete.md) |
| `/api/v1/teams.info` | Gets a team's information. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/info.md) |
| `/api/v1/teams.leave` | Leaves a team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/leave.md) |
| `/api/v1/teams.list` | Lists the public and private teams the caller is part of. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/list.md) |
| `/api/v1/teams.listAll` | Lists all of the teams and their information. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/list-all.md) |
| `/api/v1/teams.listRooms` | Lists all rooms of the team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/list-rooms.md) |
| `/api/v1/teams.listRoomsOfUser` | Lists only the team's rooms the user has joined. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/list-rooms-of-user.md) |
| `/api/v1/teams.members` | Retrieves all team members. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/members.md) |
| `/api/v1/teams.removeMember` | Removes a member from a team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/remove-member.md) |
| `/api/v1/teams.removeRoom` | Removes a room from a team. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/remove-room.md) |
| `/api/v1/teams.update` | Updates an existing team \(name and type\). | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/update.md) |
| `/api/v1/teams.updateMember` | Updates a team member's roles, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/update-member.md) |
| `/api/v1/teams.updateRoom` | Updates a room from a team, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/teams-endpoints/update-room.md) |

### Command Methods

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/commands.get` | Get specification of the slash command. | [Link](endpoints/team-collaboration-endpoints/commands-endpoints/get-lash-commands.md) |
| `/api/v1/commands.list` | Lists all available slash commands. | [Link](endpoints/team-collaboration-endpoints/commands-endpoints/list.md) |
| `/api/v1/commands.run` | Execute a slash command in the specified room. | [Link](endpoints/team-collaboration-endpoints/commands-endpoints/execute-a-slash-command.md) |

### Custom User Status

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-user-status.list` | Lists all available custom user's status. | [Link](endpoints/team-collaboration-endpoints/custom-user-status-endpoints/list.md) |

### Emoji Custom

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/emoji-custom.list` | List the custom emojis available. | [Link](endpoints/team-collaboration-endpoints/custom-emoji-endpoints/list.md) |
| `/api/v1/emoji-custom.create` | Create new custom emoji. | [Link](endpoints/team-collaboration-endpoints/custom-emoji-endpoints/create.md) |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji. | [Link](endpoints/team-collaboration-endpoints/custom-emoji-endpoints/delete.md) |
| `/api/v1/emoji-custom.update` | Update an existent custom emoji. | [Link](endpoints/team-collaboration-endpoints/custom-emoji-endpoints/update.md) |

### Settings

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/settings` | `GET` | Lists all private settings. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/get.md) |
| `/api/v1/settings.public` | `GET` | Lists all public settings. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/public.md) |
| `/api/v1/settings.oauth` | `GET` | Return list of all available oauth services. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/oauth.md) |
| `/api/v1/service.configurations` | `GET` | Lists all service configurations. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/service-configuration.md) |
| `/api/v1/settings/:_id` | `GET` | Gets a setting. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/get-by-id.md) |
| `/api/v1/settings/:_id` | `POST` | Updates a setting. | [Link](endpoints/team-collaboration-endpoints/settings-endpoints/update.md) |

### Subscriptions

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/subscriptions.get` | `GET` | Get all subscriptions. | [Link](endpoints/team-collaboration-endpoints/subscriptions-endpoints/get.md) |
| `/api/v1/subscriptions.getOne` | `GET` | Get the subscription by room Id. | [Link](endpoints/team-collaboration-endpoints/subscriptions-endpoints/getone.md) |
| `/api/v1/subscriptions.read` | `POST` | Mark a room as read. | [Link](endpoints/team-collaboration-endpoints/subscriptions-endpoints/read.md) |
| `/api/v1/subscriptions.unread` | `POST` | Mark messages as unread. | [Link](endpoints/team-collaboration-endpoints/subscriptions-endpoints/unread.md) |

### Video Conference

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/video-conference/jitsi.update-timeout` | Updates the timeout of Jitsi video conference in a channel. | [Link](endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout.md) |

### Webdav

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/webdav.getMyAccounts` | Retrieves the user's webdav accounts. | [Link](endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts.md) |

### Licenses

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/licenses.get` | `GET` | Gets all active licenses. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/licenses/get.md) |
| `/api/v1/licenses.add` | `POST` | Adds a new license. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/licenses/add.md) |

## Language specific wrappers

### Java

* [rocket-chat-rest-client](https://github.com/baloise/rocket-chat-rest-client)

### PHP

* [rocketchat-php](https://github.com/alekseykuleshov/rocket-chat)

### Python

* [rocketchat\_API](https://github.com/jadolg/rocketchat_API)
* [rocket-python](https://github.com/Pipoline/rocket-python)

### Ruby

* [rocketchat-ruby](https://github.com/abrom/rocketchat-ruby)

### Clojure

* [rocketchat-clojure](https://github.com/MalloZup/missile)

### Golang

* [rocketchat-golang](https://github.com/badkaktus/gorocket)

