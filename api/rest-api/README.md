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
| `/api/info` | Information about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/info.md) |
| `/api/v1/directory` | Search by all users and channels available on server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/directory.md) |
| `/api/v1/shield.svg` | Gets the shield svg\(badge\) to add in your website. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/shield-svg.md) |
| `/api/v1/spotlight` | Searches for users or rooms that are visible to the user. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/spotlight.md) |
| `/api/v1/statistics` | Statistics about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/statistics.md) |
| `/api/v1/statistics.list` | Selectable statistics about the Rocket.Chat server. | [Link](endpoints/team-collaboration-endpoints/miscellaneous/statistics-list.md) |
| `/api/v1/instances.get` | Gets all running instances. | [Link](https://github.com/RocketChat/docs/tree/06af028aecca9430169baa3f517704a68deb6278/api/rest-api/methods/miscellaneous/instances-get.md) |

### Assets

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | Set an asset image by name. | [Link](endpoints/team-collaboration-endpoints/assets/setasset.md) |
| `/api/v1/assets.unsetAsset` | Unset an asset by name | [Link](endpoints/team-collaboration-endpoints/assets/unset-asset.md) |

### AutoTranslate

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.getSupportedLanguages` | Get the supported languages by the autotranslate. | [Link](endpoints/team-collaboration-endpoints/autotranslate/getsupportedlanguages.md) |
| `/api/v1/autotranslate.saveSettings` | Save some settings about autotranslate. | [Link](endpoints/team-collaboration-endpoints/autotranslate/savesettings.md) |
| `/api/v1/autotranslate.translateMessage` | Translate the message. | [Link](endpoints/team-collaboration-endpoints/autotranslate/translatemessage.md) |

### Authentication

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/login` | Authenticate with the REST API. | [Link](endpoints/team-collaboration-endpoints/authentication/login.md) |
| `/api/v1/login` | Authenticate with google. | [Link](endpoints/team-collaboration-endpoints/authentication/google.md) |
| `/api/v1/login` | Authenticate with facebook. | [Link](endpoints/team-collaboration-endpoints/authentication/facebook.md) |
| `/api/v1/login` | Authenticate with twitter. | [Link](endpoints/team-collaboration-endpoints/authentication/twitter.md) |
| `/api/v1/logout` | Invalidate your REST API authentication token. | [Link](endpoints/team-collaboration-endpoints/authentication/logout.md) |
| `/api/v1/me` | Displays information about the authenticated user. | [Link](endpoints/team-collaboration-endpoints/authentication/me.md) |

### Users

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/users.presence` | Gets all connected users presence. | [Link](endpoints/team-collaboration-endpoints/users/presence.md) |
| `/api/v1/users.create` | Create a new user. | [Link](endpoints/team-collaboration-endpoints/users/create.md) |
| `/api/v1/users.createToken` | Create a user authentication token. | [Link](endpoints/team-collaboration-endpoints/users/createtoken.md) |
| `/api/v1/users.deactivateIdle` | Deactivate idle users. | [Link](endpoints/team-collaboration-endpoints/users/deactivateidle.md) |
| `/api/v1/users.delete` | Deletes an existing user. | [Link](endpoints/team-collaboration-endpoints/users/delete.md) |
| `/api/v1/users.deleteOwnAccount` | Deletes your own user account. | [Link](endpoints/team-collaboration-endpoints/users/deleteownaccount.md) |
| `/api/v1/users.forgotPassword` | Send email to reset your password. | [Link](endpoints/team-collaboration-endpoints/users/forgotpassword.md) |
| `/api/v1/users.generatePersonalAccessToken` | Generate Personal Access Token. | [Link](endpoints/team-collaboration-endpoints/users/generatepersonalaccesstoken.md) |
| `/api/v1/users.getAvatar` | Gets the URL for a user's avatar. | [Link](endpoints/team-collaboration-endpoints/users/getavatar.md) |
| `/api/v1/users.getPersonalAccessTokens` | Gets the user's personal access tokens. | [Link](endpoints/team-collaboration-endpoints/users/getpersonalaccesstokens.md) |
| `/api/v1/users.getPreferences` | Gets all preferences of user. | [Link](endpoints/team-collaboration-endpoints/users/get-preferences.md) |
| `/api/v1/users.getPresence` | Gets the online presence of a user. | [Link](endpoints/team-collaboration-endpoints/users/getpresence.md) |
| `/api/v1/users.getStatus` | Gets the user's status. | [Link](endpoints/team-collaboration-endpoints/users/getstatus.md) |
| `/api/v1/users.getUsernameSuggestion` | Gets a suggestion a new username to user. | [Link](endpoints/team-collaboration-endpoints/users/getusernamesuggestion.md) |
| `/api/v1/users.info` | Gets a user's information, limited to the caller's permissions. | [Link](endpoints/team-collaboration-endpoints/users/info.md) |
| `/api/v1/users.list` | All of the users and their information, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/users/list.md) |
| `/api/v1/users.regeneratePersonalAccessToken` | Regenerate a user personal access token. | [Link](endpoints/team-collaboration-endpoints/users/regeneratepersonalaccesstoken.md) |
| `/api/v1/users.register` | Register a new user. | [Link](endpoints/team-collaboration-endpoints/users/register.md) |
| `/api/v1/users.removeOtherTokens` | Remove all other user tokens | [Link](endpoints/team-collaboration-endpoints/users/removeothertokens.md) |
| `/api/v1/users.removePersonalAccessToken` | Remove a personal access token. | [Link](endpoints/team-collaboration-endpoints/users/removepersonalaccesstoken.md) |
| `/api/v1/users.requestDataDownload` | Request users download data. | [Link](endpoints/team-collaboration-endpoints/users/requestdatadownload.md) |
| `/api/v1/users.resetAvatar` | Reset a user's avatar | [Link](endpoints/team-collaboration-endpoints/users/resetavatar.md) |
| `/api/v1/users.setAvatar` | Set a user's avatar | [Link](endpoints/team-collaboration-endpoints/users/setavatar.md) |
| `/api/v1/users.setPreferences` | Set user's preferences | [Link](endpoints/team-collaboration-endpoints/users/set-preferences.md) |
| `/api/v1/users.setStatus` | Set the user's status | [Link](endpoints/team-collaboration-endpoints/users/setstatus.md) |
| `/api/v1/users.setActiveStatus` | Set a user's active status. | [Link](endpoints/team-collaboration-endpoints/users/setactivestatus.md) |
| `/api/v1/users.update` | Update an existing user. | [Link](endpoints/team-collaboration-endpoints/users/update.md) |
| `/api/v1/users.updateOwnBasicInfo` | Update basic information of own user. | [Link](endpoints/team-collaboration-endpoints/users/updateownbasicinfo.md) |

### Channels

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/channels.addAll` | Adds all of the users on the server to a channel. | [Link](endpoints/team-collaboration-endpoints/channels/addall.md) |
| `/api/v1/channels.addLeader` | Gives the role of Leader for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels/addleader.md) |
| `/api/v1/channels.addOwner` | Gives the role of owner for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels/addowner.md) |
| `/api/v1/channels.anonymousread` | Gets the messages in public channels to an anonymous user | [Link](endpoints/team-collaboration-endpoints/channels/anonymousread.md) |
| `/api/v1/channels.archive` | Archives a channel. | [Link](endpoints/team-collaboration-endpoints/channels/archive.md) |
| `/api/v1/channels.close` | Removes a channel from a user's list of channels. | [Link](endpoints/team-collaboration-endpoints/channels/close.md) |
| `/api/v1/channels.counters` | Gets channel counters. | [Link](endpoints/team-collaboration-endpoints/channels/counters.md) |
| `/api/v1/channels.create` | Creates a new channel. | [Link](endpoints/team-collaboration-endpoints/channels/create.md) |
| `/api/v1/channels.delete` | Removes a channel. | [Link](endpoints/team-collaboration-endpoints/channels/delete.md) |
| `/api/v1/channels.files` | Gets a list of files from a channel. | [Link](endpoints/team-collaboration-endpoints/channels/files.md) |
| `/api/v1/channels.getAllUserMentionsByChannel` | Gets all the mentions of a channel. | [Link](endpoints/team-collaboration-endpoints/channels/getallusermentionsbychannel.md) |
| `/api/v1/channels.getIntegrations` | Gets the channel's integration. | [Link](endpoints/team-collaboration-endpoints/channels/getintegrations.md) |
| `/api/v1/channels.history` | Retrieves the messages from a channel. | [Link](endpoints/team-collaboration-endpoints/channels/history.md) |
| `/api/v1/channels.info` | Gets a channel's information. | [Link](endpoints/team-collaboration-endpoints/channels/info.md) |
| `/api/v1/channels.invite` | Adds a user to a channel. | [Link](endpoints/team-collaboration-endpoints/channels/invite.md) |
| `/api/v1/channels.join` | Joins yourself to a channel. | [Link](endpoints/team-collaboration-endpoints/channels/join.md) |
| `/api/v1/channels.kick` | Removes a user from a channel. | [Link](endpoints/team-collaboration-endpoints/channels/kick.md) |
| `/api/v1/channels.leave` | Removes the calling user from a channel. | [Link](endpoints/team-collaboration-endpoints/channels/leave.md) |
| `/api/v1/channels.list` | Retrieves all of the channels from the server. | [Link](endpoints/team-collaboration-endpoints/channels/list.md) |
| `/api/v1/channels.list.joined` | Gets only the channels the calling user has joined. | [Link](endpoints/team-collaboration-endpoints/channels/list-joined.md) |
| `/api/v1/channels.members` | Retrieves all channel users. | [Link](endpoints/team-collaboration-endpoints/channels/members.md) |
| `/api/v1/channels.messages` | Retrieves all channel messages. | [Link](endpoints/team-collaboration-endpoints/channels/messages.md) |
| `/api/v1/channels.moderators` | List all moderators of a channel. | [Link](endpoints/team-collaboration-endpoints/channels/moderators.md) |
| `/api/v1/channels.online` | List all online users of a channel. | [Link](endpoints/team-collaboration-endpoints/channels/online.md) |
| `/api/v1/channels.open` | Adds the channel back to the user's list of channels. | [Link](endpoints/team-collaboration-endpoints/channels/open.md) |
| `/api/v1/channels.removeleader` | Removes the role of Leader for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels/removeleader.md) |
| `/api/v1/channels.rename` | Changes a channel's name. | [Link](endpoints/team-collaboration-endpoints/channels/rename.md) |
| `/api/v1/channels.roles` | Gets the user's roles in the channel. | [Link](endpoints/team-collaboration-endpoints/channels/roles.md) |
| `/api/v1/channels.setCustomFields` | Sets a channel's custom fields. | [Link](endpoints/team-collaboration-endpoints/channels/setcustomfields.md) |
| `/api/v1/channels.setAnnouncement` | Sets a channel's announcement. | [Link](endpoints/team-collaboration-endpoints/channels/setannouncement.md) |
| `/api/v1/channels.setDefault` | Sets whether a channel is a default channel or not. | [Link](endpoints/team-collaboration-endpoints/channels/setdefault.md) |
| `/api/v1/channels.setDescription` | Sets a channel's description. | [Link](endpoints/team-collaboration-endpoints/channels/setdescription.md) |
| `/api/v1/channels.setJoinCode` | Sets the channel's code required to join it. | [Link](endpoints/team-collaboration-endpoints/channels/setjoincode.md) |
| `/api/v1/channels.setPurpose` | Sets a channel's description. | [Link](endpoints/team-collaboration-endpoints/channels/setpurpose.md) |
| `/api/v1/channels.setReadOnly` | Sets whether a channel is read only or not. | [Link](endpoints/team-collaboration-endpoints/channels/setreadonly.md) |
| `/api/v1/channels.setTopic` | Sets a channel's topic. | [Link](endpoints/team-collaboration-endpoints/channels/settopic.md) |
| `/api/v1/channels.setType` | Sets the type of room the channel should be. | [Link](endpoints/team-collaboration-endpoints/channels/settype.md) |
| `/api/v1/channels.unarchive` | Unarchives a channel. | [Link](endpoints/team-collaboration-endpoints/channels/unarchive.md) |
| `/api/v1/channels.addOwner` | Gives the role of owner for a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels/addowner.md) |
| `/api/v1/channels.removeOwner` | Removes the role of owner from a user in the current channel. | [Link](endpoints/team-collaboration-endpoints/channels/removeowner.md) |

### Groups

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/groups.archive` | Archives a private group. | [Link](endpoints/team-collaboration-endpoints/groups/archive.md) |
| `/api/v1/groups.addLeader` | Gives the role of Leader for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups/addleader.md) |
| `/api/v1/groups.close` | Removes a private group from the list of groups. | [Link](endpoints/team-collaboration-endpoints/groups/close.md) |
| `/api/v1/groups.counters` | Gets group counters. | [Link](endpoints/team-collaboration-endpoints/groups/counters.md) |
| `/api/v1/groups.create` | Creates a new private group. | [Link](endpoints/team-collaboration-endpoints/groups/create.md) |
| `/api/v1/groups.delete` | Removes a private group. | [Link](endpoints/team-collaboration-endpoints/groups/delete.md) |
| `/api/v1/groups.files` | Gets a list of files from a private group. | [Link](endpoints/team-collaboration-endpoints/groups/files.md) |
| `/api/v1/groups.history` | Retrieves the messages from a private group. | [Link](endpoints/team-collaboration-endpoints/groups/history.md) |
| `/api/v1/groups.info` | Gets the information about a private group. | [Link](endpoints/team-collaboration-endpoints/groups/info.md) |
| `/api/v1/groups.invite` | Adds a user to the private group. | [Link](endpoints/team-collaboration-endpoints/groups/invite.md) |
| `/api/v1/groups.kick` | Removes a user from a private group. | [Link](endpoints/team-collaboration-endpoints/groups/kick.md) |
| `/api/v1/groups.leave` | Removes the calling user from the private group. | [Link](endpoints/team-collaboration-endpoints/groups/leave.md) |
| `/api/v1/groups.list` | List the private groups the caller is part of. | [Link](endpoints/team-collaboration-endpoints/groups/list.md) |
| `/api/v1/groups.listAll` | List all the private groups. | [Link](endpoints/team-collaboration-endpoints/groups/listall.md) |
| `/api/v1/groups.members` | Gets the users of participants of a private group. | [Link](endpoints/team-collaboration-endpoints/groups/members.md) |
| `/api/v1/groups.messages` | Retrieves all group messages. | [Link](endpoints/team-collaboration-endpoints/groups/messages.md) |
| `/api/v1/groups.moderators` | List all moderators of a group. | [Link](endpoints/team-collaboration-endpoints/groups/moderators.md) |
| `/api/v1/groups.online` | List all online users of a group. | [Link](https://github.com/RocketChat/docs/tree/aeb4dd8de5017b7cd9c9d9367a0e2155f911ba5a/api/rest-api/methods/groups/online.md) |
| `/api/v1/groups.open` | Adds the private group back to the list of groups. | [Link](endpoints/team-collaboration-endpoints/groups/open.md) |
| `/api/v1/groups.removeLeader` | Removes the role of Leader for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups/removeleader.md) |
| `/api/v1/groups.rename` | Changes the name of the private group. | [Link](endpoints/team-collaboration-endpoints/groups/rename.md) |
| `/api/v1/groups.roles` | Gets the user's roles in the private group. | [Link](endpoints/team-collaboration-endpoints/groups/roles.md) |
| `/api/v1/groups.setAnnouncement` | Sets a group's announcement. | [Link](endpoints/team-collaboration-endpoints/groups/setannouncement.md) |
| `/api/v1/groups.setCustomFields` | Sets private group's custom fields. | [Link](endpoints/team-collaboration-endpoints/groups/setcustomfields.md) |
| `/api/v1/groups.setDescription` | Sets a private group's description. | [Link](endpoints/team-collaboration-endpoints/groups/setdescription.md) |
| `/api/v1/groups.setPurpose` | Sets a private group's description. | [Link](endpoints/team-collaboration-endpoints/groups/setpurpose.md) |
| `/api/v1/groups.setReadOnly` | Sets whether the room is read only or not. | [Link](endpoints/team-collaboration-endpoints/groups/setreadonly.md) |
| `/api/v1/groups.setTopic` | Sets a private group's topic. | [Link](endpoints/team-collaboration-endpoints/groups/settopic.md) |
| `/api/v1/groups.setType` | Sets the type of room this group will be. | [Link](endpoints/team-collaboration-endpoints/groups/settype.md) |
| `/api/v1/groups.unarchive` | Unarchives a private group. | [Link](endpoints/team-collaboration-endpoints/groups/unarchive.md) |
| `/api/v1/groups.addOwner` | Gives the role of owner for a user in the current group. | [Link](endpoints/team-collaboration-endpoints/groups/addowner.md) |
| `/api/v1/groups.removeOwner` | Removes the role of owner from a user in the current Group. | [Link](endpoints/team-collaboration-endpoints/groups/removeowner.md) |

### Chat

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/chat.delete` | Deletes an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat/delete.md) |
| `/api/v1/chat.followMessage` | Follows an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat/followmessage.md) |
| `/api/v1/chat.getDeletedMessages` | Retrieves the deleted messages since specific date. | [Link](endpoints/team-collaboration-endpoints/chat/getdeletedmessages.md) |
| `/api/v1/chat.getDiscussions` | Retrieves the discussions messages of a room. | [Link](endpoints/team-collaboration-endpoints/chat/getdiscussions.md) |
| `/api/v1/chat.getMentionedMessages` | Retrieves mentioned messages. | [Link](endpoints/team-collaboration-endpoints/chat/getmentionedmessages.md) |
| `/api/v1/chat.getMessage` | Retrieves a single chat message. | [Link](endpoints/team-collaboration-endpoints/chat/getmessage.md) |
| `/api/v1/chat.getMessageReadReceipts` | Retrieves message read receipts. | [Link](endpoints/team-collaboration-endpoints/chat/getmessagereadreceipts.md) |
| `/api/v1/chat.getPinnedMessages` | Retrieve pinned messages from a room. | [Link](endpoints/team-collaboration-endpoints/chat/getpinnedmessages.md) |
| `/api/v1/chat.getSnippetedMessages` | Retrieves snippeted messages. | [Link](endpoints/team-collaboration-endpoints/chat/getsnippetedmessages.md) |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippeted message by id. | [Link](endpoints/team-collaboration-endpoints/chat/getsnippetedmessagebyid.md) |
| `/api/v1/chat.getStarredMessages` | Retrieves starred messages. | [Link](endpoints/team-collaboration-endpoints/chat/getstarredmessages.md) |
| `/api/v1/chat.getThreadMessages` | Retrieves thread's messages. | [Link](endpoints/team-collaboration-endpoints/chat/getthreadmessages.md) |
| `/api/v1/chat.getThreadsList` | Retrieves channel's threads. | [Link](endpoints/team-collaboration-endpoints/chat/getthreadslist.md) |
| `/api/v1/chat.ignoreUser` | Ignores an user from a chat. | [Link](endpoints/team-collaboration-endpoints/chat/ignoreuser.md) |
| `/api/v1/chat.pinMessage` | Pins a chat message to the message's channel. | [Link](endpoints/team-collaboration-endpoints/chat/pinmessage.md) |
| `/api/v1/chat.postMessage` | Posts a new chat message. | [Link](endpoints/team-collaboration-endpoints/chat/postmessage.md) |
| `/api/v1/chat.react` | Sets/unsets the user's reaction to an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat/react.md) |
| `/api/v1/chat.reportMessage` | Reports a message. | [Link](endpoints/team-collaboration-endpoints/chat/reportmessage.md) |
| `/api/v1/chat.search` | Search for messages in a channel. | [Link](endpoints/team-collaboration-endpoints/chat/search.md) |
| `/api/v1/chat.starMessage` | Stars a chat message for the authenticated user. | [Link](endpoints/team-collaboration-endpoints/chat/starmessage.md) |
| `/api/v1/chat.sendMessage` | Send new chat message. | [Link](endpoints/team-collaboration-endpoints/chat/sendmessage.md) |
| `/api/v1/chat.syncThreadMessages` | Retrieves synced thread's messages. | [Link](endpoints/team-collaboration-endpoints/chat/syncthreadmessages.md) |
| `/api/v1/chat.syncThreadsList` | Retrieves thread's synced channel threads. | [Link](endpoints/team-collaboration-endpoints/chat/syncthreadslist.md) |
| `/api/v1/chat.unfollowMessage` | Unfollows an existing chat message. | [Link](endpoints/team-collaboration-endpoints/chat/unfollowmessage.md) |
| `/api/v1/chat.unPinMessage` | Removes the pinned status of the provided chat message. | [Link](endpoints/team-collaboration-endpoints/chat/unpinmessage.md) |
| `/api/v1/chat.unStarMessage` | Removes the star on the chat message for the authenticated user. | [Link](endpoints/team-collaboration-endpoints/chat/unstarmessage.md) |
| `/api/v1/chat.update` | Updates the text of the chat message. | [Link](endpoints/team-collaboration-endpoints/chat/update.md) |

### Custom Sounds

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | [Link](endpoints/team-collaboration-endpoints/custom-sounds/custom-sounds-list.md) |

### IM

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/im.close` | Removes a direct message from the list of direct messages. | [Link](endpoints/team-collaboration-endpoints/im/close.md) |
| `/api/v1/im.counters` | Gets counters of direct messages. | [Link](endpoints/team-collaboration-endpoints/im/counters.md) |
| `/api/v1/im.create` | Create a direct message session with another user. | [Link](endpoints/team-collaboration-endpoints/im/create.md) |
| `/api/v1/im.history` | Retrieves the messages from a direct message. | [Link](endpoints/team-collaboration-endpoints/im/history.md) |
| `/api/v1/im.files` | Retrieves a list of files from a direct message. | [Link](endpoints/team-collaboration-endpoints/im/files.md) |
| `/api/v1/im.members` | Retrieves the users of participants of a direct message. | [Link](endpoints/team-collaboration-endpoints/im/members.md) |
| `/api/v1/im.messages` | Retrieves the messages from specific direct message. | [Link](endpoints/team-collaboration-endpoints/im/messages.md) |
| `/api/v1/im.messages.others` | Retrieves the messages from any direct message in the server. | [Link](endpoints/team-collaboration-endpoints/im/messages-others.md) |
| `/api/v1/im.list` | List the direct messages the caller is part of. | [Link](endpoints/team-collaboration-endpoints/im/list.md) |
| `/api/v1/im.list.everyone` | List all direct message the caller in the server. | [Link](endpoints/team-collaboration-endpoints/im/list-everyone.md) |
| `/api/v1/im.open` | Adds the direct message back to the list of direct messages. | [Link](endpoints/team-collaboration-endpoints/im/open.md) |
| `/api/v1/im.setTopic` | Sets a direct message topic. | [Link](endpoints/team-collaboration-endpoints/im/settopic.md) |

### Integrations

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/integrations.create` | Creates an integration. | [Link](endpoints/team-collaboration-endpoints/integration/create.md) |
| `/api/v1/integrations.get` | Gets an integration. | [Link](endpoints/team-collaboration-endpoints/integration/get.md) |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](endpoints/team-collaboration-endpoints/integration/history.md) |
| `/api/v1/integrations.list` | Lists all of the integrations. | [Link](endpoints/team-collaboration-endpoints/integration/list.md) |
| `/api/v1/integrations.remove` | Removes an integration. | [Link](endpoints/team-collaboration-endpoints/integration/remove.md) |

### Invites

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/findOrCreateInvite` | Created a new Invite or returns an existing one with the same parameters. | [Link](endpoints/team-collaboration-endpoints/invites/findorcreateinvite.md) |
| `/api/v1/listInvites` | Lists all of the invite tokens. | [Link](endpoints/team-collaboration-endpoints/invites/listinvites.md) |
| `/api/v1/removeInvite` | Removes an invite. | [Link](endpoints/team-collaboration-endpoints/invites/removeinvite.md) |
| `/api/v1/useInviteToken` | Report to the server that an invite token was used. | [Link](endpoints/team-collaboration-endpoints/invites/useinvitetoken.md) |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid. | [Link](endpoints/team-collaboration-endpoints/invites/validateinvitetoken.md) |

### Livechat

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.list` | Retrieves a list of open inquiries. | [Link](endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list.md#inquiries-list) |
| `/api/v1/livechat/inquiries.take` | Take an open inquiry. | [Link](endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list.md#livechat-take-inquiry) |
| `/api/v1/livechat/rooms` | Retrieves a list of livechat rooms. | [Link](endpoints/omnichannel/omnichannel-endpoints/rooms/) |

### OAuthApps

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/oauth-apps.get` | Retrieves an OAuth App by id or client id. | [Link](endpoints/team-collaboration-endpoints/oauthapps/get.md) |
| `/api/v1/oauth-apps.list` | Retrieves a list of OAuth Apps. | [Link](endpoints/team-collaboration-endpoints/oauthapps/list.md) |

### Permissions

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](endpoints/team-collaboration-endpoints/permissions/listall.md) |
| `/api/v1/permissions.update` | Edits permissions on the server. | [Link](endpoints/team-collaboration-endpoints/permissions/update.md) |

### Roles

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/roles.create` | Create a new role in the system. | [Link](endpoints/team-collaboration-endpoints/roles/create.md) |
| `/api/v1/roles.list` | Gets all the roles in the system. | [Link](endpoints/team-collaboration-endpoints/roles/list.md) |
| `/api/v1/roles.sync` | Gets all the roles in the system which are updated after a given date. | [Link](endpoints/team-collaboration-endpoints/roles/sync.md) |
| `/api/v1/roles.addUserToRole` | Assign a role to an user. | [Link](endpoints/team-collaboration-endpoints/roles/addusertorole.md) |
| `/api/v1/roles.getUsersInRole` | Gets the users that belongs to a role. | [Link](endpoints/team-collaboration-endpoints/roles/getusersinrole.md) |
| `/api/v1/roles.update` | Update an existing role in the system. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/update.md) |
| `/api/v1/roles.delete` | Delete a role. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/delete.md) |

### Push Token

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/push.token` | `POST` | Saves push token. | [Link](endpoints/team-collaboration-endpoints/push/push-token.md) |
| `/api/v1/push.token` | `DELETE` | Removes push token. | [Link](endpoints/team-collaboration-endpoints/push/deletepushtoken.md) |

### Rooms

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/rooms.adminRooms` | Retrieve all rooms \(requires special permission\). | [Link](endpoints/team-collaboration-endpoints/rooms/adminrooms.md) |
| `/api/v1/rooms.cleanHistory` | Cleans up a room's history, requires special permission. | [Link](endpoints/team-collaboration-endpoints/rooms/cleanhistory.md) |
| `/api/v1/rooms.createDiscussion` | Creates a new discussion. | [Link](endpoints/team-collaboration-endpoints/rooms/creatediscussion.md) |
| `/api/v1/rooms.favorite` | Favorite/Unfavorite room. | [Link](endpoints/team-collaboration-endpoints/rooms/favorite.md) |
| `/api/v1/rooms.get` | Gets rooms. | [Link](endpoints/team-collaboration-endpoints/rooms/get.md) |
| `/api/v1/rooms.getDiscussions` | Gets room's discussions. | [Link](endpoints/team-collaboration-endpoints/rooms/getdiscussions.md) |
| `/api/v1/rooms.info` | Gets info from a room. | [Link](endpoints/team-collaboration-endpoints/rooms/info.md) |
| `/api/v1/rooms.leave` | Leaves a room. | [Link](endpoints/team-collaboration-endpoints/rooms/leave.md) |
| `/api/v1/rooms.saveNotification` | Sets the notifications settings of specific channel. | [Link](endpoints/team-collaboration-endpoints/rooms/savenotification.md) |
| `/api/v1/rooms.upload/:rid` | Upload a message with attached file. | [Link](endpoints/team-collaboration-endpoints/rooms/upload.md) |

### Teams

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/teams.addMembers` | Adds users to the team. | [Link](endpoints/team-collaboration-endpoints/teams/add-members.md) |
| `/api/v1/teams.addRooms` | Adds rooms to the team. | [Link](endpoints/team-collaboration-endpoints/teams/add-rooms.md) |
| `/api/v1/teams.autocomplete` | Lists the teams whose names match a given pattern. | [Link](endpoints/team-collaboration-endpoints/teams/autocomplete.md) |
| `/api/v1/teams.create` | Creates a new team. | [Link](endpoints/team-collaboration-endpoints/teams/create.md) |
| `/api/v1/teams.delete` | Removes a team. | [Link](endpoints/team-collaboration-endpoints/teams/delete.md) |
| `/api/v1/teams.info` | Gets a team's information. | [Link](endpoints/team-collaboration-endpoints/teams/info.md) |
| `/api/v1/teams.leave` | Leaves a team. | [Link](endpoints/team-collaboration-endpoints/teams/leave.md) |
| `/api/v1/teams.list` | Lists the public and private teams the caller is part of. | [Link](endpoints/team-collaboration-endpoints/teams/list.md) |
| `/api/v1/teams.listAll` | Lists all of the teams and their information. | [Link](endpoints/team-collaboration-endpoints/teams/list-all.md) |
| `/api/v1/teams.listRooms` | Lists all rooms of the team. | [Link](endpoints/team-collaboration-endpoints/teams/list-rooms.md) |
| `/api/v1/teams.listRoomsOfUser` | Lists only the team's rooms the user has joined. | [Link](endpoints/team-collaboration-endpoints/teams/list-rooms-of-user.md) |
| `/api/v1/teams.members` | Retrieves all team members. | [Link](endpoints/team-collaboration-endpoints/teams/members.md) |
| `/api/v1/teams.removeMember` | Removes a member from a team. | [Link](endpoints/team-collaboration-endpoints/teams/remove-member.md) |
| `/api/v1/teams.removeRoom` | Removes a room from a team. | [Link](endpoints/team-collaboration-endpoints/teams/remove-room.md) |
| `/api/v1/teams.update` | Updates an existing team \(name and type\). | [Link](endpoints/team-collaboration-endpoints/teams/update.md) |
| `/api/v1/teams.updateMember` | Updates a team member's roles, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/teams/update-member.md) |
| `/api/v1/teams.updateRoom` | Updates a room from a team, limited to permissions. | [Link](endpoints/team-collaboration-endpoints/teams/update-room.md) |

### Command Methods

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/commands.get` | Get specification of the slash command. | [Link](endpoints/team-collaboration-endpoints/commands/get.md) |
| `/api/v1/commands.list` | Lists all available slash commands. | [Link](endpoints/team-collaboration-endpoints/commands/list.md) |
| `/api/v1/commands.run` | Execute a slash command in the specified room. | [Link](endpoints/team-collaboration-endpoints/commands/run.md) |

### Custom User Status

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-user-status.list` | Lists all available custom user's status. | [Link](endpoints/team-collaboration-endpoints/custom-user-status/list.md) |

### Emoji Custom

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/emoji-custom.list` | List the custom emojis available. | [Link](endpoints/team-collaboration-endpoints/emoji-custom/list.md) |
| `/api/v1/emoji-custom.create` | Create new custom emoji. | [Link](endpoints/team-collaboration-endpoints/emoji-custom/create.md) |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji. | [Link](endpoints/team-collaboration-endpoints/emoji-custom/delete.md) |
| `/api/v1/emoji-custom.update` | Update an existent custom emoji. | [Link](endpoints/team-collaboration-endpoints/emoji-custom/update.md) |

### Settings

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/settings` | `GET` | Lists all private settings. | [Link](endpoints/team-collaboration-endpoints/settings/get.md) |
| `/api/v1/settings.public` | `GET` | Lists all public settings. | [Link](endpoints/team-collaboration-endpoints/settings/public.md) |
| `/api/v1/settings.oauth` | `GET` | Return list of all available oauth services. | [Link](endpoints/team-collaboration-endpoints/settings/oauth.md) |
| `/api/v1/service.configurations` | `GET` | Lists all service configurations. | [Link](endpoints/team-collaboration-endpoints/settings/service-configuration.md) |
| `/api/v1/settings/:_id` | `GET` | Gets a setting. | [Link](endpoints/team-collaboration-endpoints/settings/get-by-id.md) |
| `/api/v1/settings/:_id` | `POST` | Updates a setting. | [Link](endpoints/team-collaboration-endpoints/settings/update.md) |

### Subscriptions

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/subscriptions.get` | `GET` | Get all subscriptions. | [Link](endpoints/team-collaboration-endpoints/subscriptions/get.md) |
| `/api/v1/subscriptions.getOne` | `GET` | Get the subscription by room Id. | [Link](endpoints/team-collaboration-endpoints/subscriptions/getone.md) |
| `/api/v1/subscriptions.read` | `POST` | Mark a room as read. | [Link](endpoints/team-collaboration-endpoints/subscriptions/read.md) |
| `/api/v1/subscriptions.unread` | `POST` | Mark messages as unread. | [Link](endpoints/team-collaboration-endpoints/subscriptions/unread.md) |

### Video Conference

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/video-conference/jitsi.update-timeout` | Updates the timeout of Jitsi video conference in a channel. | [Link](endpoints/team-collaboration-endpoints/video-conference/jitsi-update-timeout.md) |

### Webdav

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/webdav.getMyAccounts` | Retrieves the user's webdav accounts. | [Link](endpoints/team-collaboration-endpoints/webdav/getmyaccounts.md) |

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

