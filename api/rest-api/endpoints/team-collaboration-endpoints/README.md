# Team Collaboration Endpoints

## Assets Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | Set an asset image by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset) |
| `/api/v1/assets.unsetAsset` | Unset an asset by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset) |

## Auto Translate Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.getSupportedLanguages` | Get the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings` | Save some settings about auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings) |
| `/api/v1/autotranslate.translateMessage` | Translate the message. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage) |

## Banners Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/banners.getNew` | Get  | Document Under Development |
| `/api/v1/banners.dismiss` | Post | Document Under Development |

## Channels Endpoints

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
| `/api/v1/channels.removeModerator` | Removes the role of moderator from a user in a channel. | [Link](channels-endpoints/removemoderator.md) |
| `/api/v1/channels.removeOwner` | Removes the role of owner from a user in a channel. | [Link](channels-endpoints/removeowner.md) |
| `/api/v1/channels.rename` | Changes a channel's name. | [Link](channels-endpoints/rename.md) |
| `/api/v1/channels.roles` | Gets the user's roles in the channel. | [Link](channels-endpoints/roles.md) |
| `/api/v1/channels.setAnnouncement` | Sets a channel's announcement. | [Link](channels-endpoints/setannouncement.md) |
| `/api/v1/channels.setCustomFields` | Sets a channel's custom fields. | [Link](channels-endpoints/setcustomfields.md) |
| `/api/v1/channels.setDefault` | Sets a channel's default status. | [Link](channels-endpoints/setdefault.md) |
| `/api/v1/channels.setDescription` | Sets a channel's description. | [Link](channels-endpoints/setdescription.md) |
| `/api/v1/channels.setJoinCode` | Sets the channel's code required to join it. | [Link](channels-endpoints/setjoincode.md) |
| `/api/v1/channels.setPurpose` | Sets a channel's description. | [Link](channels-endpoints/setpurpose.md) |
| `/api/v1/channels.setReadOnly` | Sets whether a channel is read-only or not. | [Link](channels-endpoints/setreadonly.md) |
| `/api/v1/channels.setTopic` | Sets a channel's topic. | [Link](channels-endpoints/settopic.md) |
| `/api/v1/channels.setType` | Sets the type of room the channel should be. | [Link](channels-endpoints/settype.md) |
| `/api/v1/channels.unarchive` | Unarchives a channel. | [Link](channels-endpoints/unarchive.md) |
| `/api/v1/channels.convertToTeam` | Convert channel to team | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/channels-endpoints/convert-channel-to-team) |

## Chat Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/chat.delete` | Deletes an existing chat message. | [Link](chat-endpoints/delete.md) |
| `/api/v1/chat.followMessage` | Follows an existing chat message. | [Link](chat-endpoints/followmessage.md) |
| `/api/v1/chat.getDeletedMessages` | Retrieves the deleted messages from a specific date. | [Link](chat-endpoints/getdeletedmessages.md) |
| `/api/v1/chat.getDiscussions` | Retrieves the discussions of a room. | [Link](chat-endpoints/getdiscussions.md) |
| `/api/v1/chat.getMentionedMessages` | Retrieves the mentioned messages. | [Link](chat-endpoints/getmentionedmessages.md) |
| `/api/v1/chat.getMessage` | Retrieves a single chat message. | [Link](chat-endpoints/getmessage.md) |
| `/api/v1/chat.getMessageReadReceipts` | Retrieves message read receipts. | [Link](chat-endpoints/getmessagereadreceipts.md) |
| `/api/v1/chat.getPinnedMessages` | Retrieve pinned messages from a room. | [Link](chat-endpoints/getpinnedmessages.md) |
| `/api/v1/chat.getSnippetedMessages` | Retrieves snippeted messages. | [Link](chat-endpoints/getsnippetedmessages.md) |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippeted message by id. | [Link](chat-endpoints/getsnippetedmessagebyid.md) |
| `/api/v1/chat.getStarredMessages` | Retrieves the starred messages. | [Link](chat-endpoints/getstarredmessages.md) |
| `/api/v1/chat.getThreadMessages` | Retrieves thread's messages. | [Link](chat-endpoints/getthreadmessages.md) |
| `/api/v1/chat.getThreadsList` | Retrieves channel's threads. | [Link](chat-endpoints/getthreadslist.md) |
| `/api/v1/chat.ignoreUser` | Ignores abuser from a chat. | [Link](chat-endpoints/ignoreuser.md) |
| `/api/v1/chat.pinMessage` | Pins a chat message to the message's channel. | [Link](chat-endpoints/pinmessage.md) |
| `/api/v1/chat.postMessage` | Posts a new chat message. | [Link](chat-endpoints/postmessage.md) |
| `/api/v1/chat.react` | Sets/unsets the user's reaction to an existing chat message. | [Link](chat-endpoints/chat-message-reactions.md) |
| `/api/v1/chat.reportMessage` | Reports a message. | [Link](chat-endpoints/reportmessage.md) |
| `/api/v1/chat.search` | Search for messages in a channel. | [Link](chat-endpoints/search-message.md) |
| `/api/v1/chat.starMessage` | Stars a chat message for the authenticated user. | [Link](chat-endpoints/starmessage.md) |
| `/api/v1/chat.sendMessage` | Send a new chat message. | [Link](chat-endpoints/sendmessage.md) |
| `/api/v1/chat.syncThreadMessages` | Retrieves synced thread's messages. | [Link](chat-endpoints/syncthreadmessages.md) |
| `/api/v1/chat.syncThreadsList` | Retrieves thread's synced channel threads. | [Link](chat-endpoints/syncthreadslist.md) |
| `/api/v1/chat.unfollowMessage` | Unfollows an existing chat message. | [Link](chat-endpoints/unfollowmessage.md) |
| `/api/v1/chat.unPinMessage` | Removes the pinned status of the provided chat message. | [Link](chat-endpoints/unpinmessage.md) |
| `/api/v1/chat.unStarMessage` | Removes the star on the chat message for the authenticated user. | [Link](chat-endpoints/unstarmessage.md) |
| `/api/v1/chat.update` | Updates the text of the chat message. | [Link](chat-endpoints/message-update.md) |
| `/api/v1/chat.syncMessages` | get | Document Under Development |

## Cloud Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/cloud.manualRegister` | Post | Document Under Development |

## Commands Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/commands.get` | Get the specification of the slash command. | [Link](commands-endpoints/get-lash-commands.md) |
| `/api/v1/commands.list` | Lists all available slash commands. | [Link](commands-endpoints/list.md) |
| `/api/v1/commands.run` | Execute a slash command in the specified room. | [Link](commands-endpoints/execute-a-slash-command.md) |
| `/api/v1/commands.preview` | Gets the preview data for the command and executes the preview item. | [Link](commands-endpoints/preview.md) |
| `/api/v1/commands.preview` | Execute command's preview item | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/commands/execute-commands-preview-item) |

## Custom Sounds Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | ​[Link](https://app.gitbook.com/@rocket-chat/s/rocket-chat-developer/~/drafts/-MgSmy428hAP1znS6g3V/api/rest-api/endpoints/team-collaboration/custom-sounds/list)​ |

## Custom User Status Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/custom-user-status.list` | Lists all available custom user's status. | [Link](custom-user-status-endpoints/list.md) |
| `/api/v1/custom-user-status.create` | post | Document Under Development |
| `/api/v1/custom-user-status.delete` | post | Document Under Development |
| `/api/v1/custom-user-status.update` | post | Document Under Development |

## DNS Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/dns.resolve.srv` | get | Document Under Development |
| `/api/v1/dns.resolve.txt` | post | Document Under Development |

## E2E Endpoints



| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/e2e.fetchMyKeys` | get | Document Under Development |
| `/api/v1/e2e.getUsersOfRoomWithoutKey` | post | Document Under Development |
| `/api/v1/e2e.setRoomKeyID` | post | Document Under Development |
| `/api/v1/e2e.setUserPublicAndPrivateKeys` | post | Document Under Development |
| `/api/v1/e2e.updateGroupKey` | post | Document Under Development |



## Email Inbox Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/email-inbox.list` | get | Document Under Development |
| `/api/v1/email-inbox` | post | Document Under Development |
| `/api/v1/email-inbox/:_id` | get | Document Under Development |
| `/api/v1/email-inbox/:_id` | delete | Document Under Development |
| `/api/v1/email-inbox.search` | get | Document Under Development |
| `/api/v1/email-inbox.send-test/:_id` | post | Document Under Development |

## Custom Emojis Endpoints <a id="email-inbox-endpoints"></a>



| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/emoji-custom` | get | Document Under Development |
| `/api/v1/emoji-custom.all` | get | Document Under Development |
| `/api/v1/emoji-custom.list` | List all custom emojis on the server. | [Link](custom-emoji-endpoints/list.md) |
| `/api/v1/emoji-custom.create` | Create new custom emoji. | [Link](custom-emoji-endpoints/create.md) |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji. | [Link](custom-emoji-endpoints/delete.md) |
| `/api/v1/emoji-custom.update` | Update an existent custom emoji. | [Link](custom-emoji-endpoints/update.md) |

## Groups Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/groups.addAll` | Adds all of the users on the server to a private group. | [Link](groups-endpoints/addall.md) |
| `/api/v1/groups.addLeader` | Gives the role of Leader for a user in the current group. | [Link](groups-endpoints/addleader.md) |
| `/api/v1/groups.addModerator` | Gives the role of moderator to a user in a group. | [Link](groups-endpoints/addmoderator.md) |
| `/api/v1/groups.addOwner` | Gives the role of owner to a user in a group. | [Link](groups-endpoints/addowner.md) |
| `/api/v1/groups.archive` | Archives a private group. | [Link](groups-endpoints/archive.md) |
| `/api/v1/groups.close` | Removes a private group from the list of groups. | [Link](groups-endpoints/close.md) |
| `/api/v1/groups.counters` | Gets group counters. | [Link](groups-endpoints/counters.md) |
| `/api/v1/groups.create` | Creates a new private group. | [Link](groups-endpoints/create.md) |
| `/api/v1/groups.delete` | Removes a private group. | [Link](groups-endpoints/delete.md) |
| `/api/v1/groups.files` | Gets a list of files from a private group. | [Link](groups-endpoints/files.md) |
| `/api/v1/groups.getIntegrations` | Gets the integrations assigned to the group. | [Link](groups-endpoints/getintegrations.md) |
| `/api/v1/groups.history` | Retrieves the messages from a private group. | [Link](groups-endpoints/history.md) |
| `/api/v1/groups.info` | Gets the information about a private group. | [Link](groups-endpoints/info.md) |
| `/api/v1/groups.invite` | Adds a user to the private group. | [Link](groups-endpoints/invite.md) |
| `/api/v1/groups.kick` | Removes a user from a private group. | [Link](groups-endpoints/kick.md) |
| `/api/v1/groups.leave` | Removes the calling user from the private group. | [Link](groups-endpoints/leave.md) |
| `/api/v1/groups.list` | List the private groups the caller is part of. | [Link](groups-endpoints/list.md) |
| `/api/v1/groups.listAll` | List all the private groups. | [Link](groups-endpoints/listall.md) |
| `/api/v1/groups.moderators` | List all moderators of a group. | [Link](groups-endpoints/moderators.md) |
| `/api/v1/groups.members` | Gets the users of participants of a private group. | [Link](groups-endpoints/members.md) |
| `/api/v1/groups.messages` | Retrieves all group messages. | [Link](groups-endpoints/messages.md) |
| `/api/v1/groups.online` | List all online users of a group. | [Link](https://github.com/RocketChat/docs/tree/aeb4dd8de5017b7cd9c9d9367a0e2155f911ba5a/api/rest-api/methods/groups/online.md) |
| `/api/v1/groups.open` | Adds the private group back to the list of groups. | [Link](groups-endpoints/open.md) |
| `/api/v1/groups.removeLeader` | Removes the role of Leader for a user in the current group. | [Link](groups-endpoints/removeleader.md) |
| `/api/v1/groups.removeModerator` | Removes the role of moderator from a user in a group. | [Link](groups-endpoints/removemoderator.md) |
| `/api/v1/groups.removeOwner` | Removes the role of owner from a user in a group. | [Link](groups-endpoints/removeowner.md) |
| `/api/v1/groups.rename` | Changes the name of the private group. | [Link](groups-endpoints/rename.md) |
| `/api/v1/groups.roles` | Gets the user's roles in the private group. | [Link](groups-endpoints/roles.md) |
| `/api/v1/groups.setAnnouncement` | Sets a group's announcement. | [Link](groups-endpoints/setannouncement.md) |
| `/api/v1/groups.setCustomFields` | Sets private group's custom fields. | [Link](groups-endpoints/setcustomfields.md) |
| `/api/v1/groups.setDescription` | Sets a private group's description. | [Link](groups-endpoints/setdescription.md) |
| `/api/v1/groups.setPurpose` | Sets a private group's description. | [Link](groups-endpoints/setpurpose.md) |
| `/api/v1/groups.setReadOnly` | Sets whether the room is read-only or not. | [Link](groups-endpoints/setreadonly.md) |
| `/api/v1/groups.setTopic` | Sets a private group's topic. | [Link](groups-endpoints/settopic.md) |
| `/api/v1/groups.setType` | Sets the type of room this group will be. | [Link](groups-endpoints/settype.md) |
| `/api/v1/groups.unarchive` | Unarchives a private group. | [Link](groups-endpoints/unarchive.md) |
| `/api/v1/groups.setEncrypted` | \`\` | Document Under Development |
| `/api/v1/groups.convertToTeam` |  | Document Under Development |

## IM Endpoints <a id="email-inbox-endpoints"></a>



| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/im.delete` | post | Document Under Development |
| `/api/v1/im.close` | Removes a direct message from the list of direct messages. | [Link](im-endpoints/close.md) |
| `/api/v1/im.counters` | Gets counters of direct messages. | [Link](im-endpoints/counters.md) |
| `/api/v1/im.create` | Create a direct message session with another user. | [Link](im-endpoints/create.md) |
| `/api/v1/im.history` | Retrieves the messages from a direct message. | [Link](im-endpoints/history.md) |
| `/api/v1/im.files` | Retrieves a list of files from a direct message. | [Link](im-endpoints/files.md) |
| `/api/v1/im.members` | Retrieves the users of participants of a direct message. | [Link](im-endpoints/members.md) |
| `/api/v1/im.messages` | Retrieves the messages from the specific direct messages. | [Link](im-endpoints/messages.md) |
| `/api/v1/im.messages.others` | Retrieves the messages from any direct message in the server. | [Link](im-endpoints/messages-others.md) |
| `/api/v1/im.list` | List the direct messages the caller is part of. | [Link](im-endpoints/list.md) |
| `/api/v1/im.list.everyone` | List all direct messages the caller in the server. | [Link](im-endpoints/list-everyone.md) |
| `/api/v1/im.open` | Adds the direct message back to the list of direct messages. | [Link](im-endpoints/open.md) |
| `/api/v1/im.setTopic` | Sets a direct message topic. | [Link](im-endpoints/settopic.md) |

## Notes

From version 0.50.0 and on you can call the methods using `dm` instead of `im`.

## Imports Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/uploadImportFile` | `​Content` | Document Under Development |
| `​/api/v1/downloadPublicImportFile` | `​Content` | Document Under Development |
| `​/api/v1/startImport` | `​Content` | Document Under Development |
| `​/api/v1/getImportFileData` | `​Content` | Document Under Development |
| `​/api/v1/getImportProgress` | `​Content` | Document Under Development |
| `​/api/v1/getLatestImportOperations` | `​Content` | Document Under Development |
| `​/api/v1/downloadPendingFiles` | `​Content` | Document Under Development |
| `​/api/v1/downloadPendingAvatars` | `​Content` | Document Under Development |
| `​/api/v1/getCurrentImportOperation` | ​Content | Document Under Development |

## **Instances** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/instances.get` | ​get | Document Under Development |

## **Integrations** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/integrations.create` | Creates an integration. | [Link](integration-endpoints/create.md) |
| `/api/v1/integrations.get` | Gets an integration. | [Link](integration-endpoints/get.md) |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](integration-endpoints/history.md) |
| `/api/v1/integrations.list` | Lists all of the integrations. | [Link](integration-endpoints/list.md) |
| `/api/v1/integrations.remove` | Removes an integration. | [Link](integration-endpoints/remove.md) |
| `/api/v1/integrations.update` | put | Document Under Development |

## **Invites** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/findOrCreateInvite` | Created a new Invite or returns an existing one with the same parameters. | [Link](invite-endpoints/findorcreateinvite.md) |
| `/api/v1/listInvites` | Lists all of the invite tokens. | [Link](invite-endpoints/listinvites.md) |
| `/api/v1/removeInvite/:_id` | delete | Document Under Development |
| `/api/v1/useInviteToken` | Report to the server that an invite token was used. | [Link](invite-endpoints/useinvitetoken.md) |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid. | [Link](invite-endpoints/validateinvitetoken.md) |

## **Misc** Endpoints <a id="email-inbox-endpoints"></a>

Just some generic information, such as information about the server and authenticated user.

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/directory` | Search by all users and channels available on server. | [Link](miscellaneous-endpoints/directory.md) |
| `/api/info` | Information about the Rocket.Chat server. | [Link](miscellaneous-endpoints/info.md) |
| `/api/v1/shield.svg` | Gets the shield SVG \(badge\) to add in your website. | [Link](miscellaneous-endpoints/shield-svg.md) |
| `/api/v1/spotlight` | Searches for users or rooms that are visible to the user. | [Link](miscellaneous-endpoints/spotlight.md) |
| `/api/v1/me` | get | Document Under Development |
| `/api/v1/stdout.queue` | get | Document Under Development |
| `/api/v1/stdout.queue` | post | Document Under Development |

## **Oauth apps** Endpoints <a id="email-inbox-endpoints"></a>



| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/oauth-apps.get` | Retrieves an OAuth App by id or client id. | [Link](oauthapps-endpoints/get.md) |
| `/api/v1/oauth-apps.list` | Retrieves a list of OAuth Apps. | [Link](oauthapps-endpoints/list.md) |

## **Permissions** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/permissions` | `get` | Document Under Development |
| `/api/v1/permissions.list` | get | Document Under Development |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](permissions-endpoints/listall.md) |
| `/api/v1/permissions.update` | Edits permissions on the server. | [Link](permissions-endpoints/update.md) |

## **Push** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/push.token` | `POST` | Saves push token. | [Link](push-token-endpoints/push-token.md) |
| `/api/v1/push.token` | `DELETE` | Removes push token. | [Link](push-token-endpoints/deletepushtoken.md) |
| `/api/v1/push.get` | get |  | Document Under Development |

## **Roles** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/roles.list` | List all roles on the server. | [Link](roles-endpoints/list.md) |
| `/api/v1/roles.sync` | List all roles on the server which are updated after a given date. | [Link](roles-endpoints/sync.md) |
| `/api/v1/roles.create` | Create a new role. | [Link](roles-endpoints/create.md) |
| `/api/v1/roles.addUserToRole` | Edits permissions on the server. | [Link](roles-endpoints/addusertorole.md) |
| `/api/v1/roles.getUsersInRole` | Gets the users that belong to a role. | [Link](roles-endpoints/getusersinrole.md) |
| `/api/v1/roles.update` | Update an existing role in the system. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/update.md) |
| `/api/v1/roles.delete` | Delete a role. | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/delete.md) |
| `/api/v1/roles.removeUserFromRole` | Unassign a role from a user. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/roles-endpoints/role-remove) |

## **Rooms** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/rooms.adminRooms` | `GET` | Retrieve all rooms \(requires special permission\). | [Link](rooms-endpoints/adminrooms.md) |
| `/api/v1/rooms.cleanHistory` | `POST` | Cleans up a room's history, requires special permission. | [Link](rooms-endpoints/clean-room-history.md) |
| `/api/v1/rooms.createDiscussion` | `POST` | Creates a new discussion. | [Link](rooms-endpoints/creatediscussion.md) |
| `/api/v1/rooms.favorite` | `POST` | Favorite/Unfavorite room. | [Link](rooms-endpoints/favorite-unfavourite-a-room.md) |
| `/api/v1/rooms.get` | `GET` | Gets rooms. | [Link](rooms-endpoints/get-rooms.md) |
| `/api/v1/rooms.getDiscussions` | `GET` | Gets room's discussions. | [Link](rooms-endpoints/getdiscussions.md) |
| `/api/v1/rooms.info` | `GET` | Gets info from a room. | [Link](rooms-endpoints/info.md) |
| `/api/v1/rooms.leave` | `POST` | Leaves a room. | [Link](rooms-endpoints/leave-room.md) |
| `/api/v1/rooms.saveNotification` | `POST` | Sets the notification settings of specific channel. | [Link](rooms-endpoints/save-room-notification.md) |
| `/api/v1/rooms.upload/:rid` | `POST` | Upload a message with attached file. | [Link](rooms-endpoints/upload-file-to-a-room.md) |
| `/api/v1/rooms.adminRooms.getRoom` | `GET` | \`\` | Document Under Development |
| `/api/v1/rooms.autocomplete.channelAndPrivate` | `GET` | \`\` | Document Under Development |
| `/api/v1/rooms.autocomplete.availableForTeams` | `GET` | \`\` | Document Under Development |
| `/api/v1/rooms.saveRoomSettings` | `POST` | \`\` | Document Under Development |
| `/api/v1/rooms.changeArchivationState` | `POST` | \`\` | Document Under Development |
| `/api/v1/rooms.export` | `POST` |  | Document Under Development |

## **Settings** Endpoints <a id="email-inbox-endpoints"></a>



You can get and update the settings via the REST API, only if you have permission to.

| Url | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| `/api/v1/settings` | `GET` | Lists all private settings. | [Link](settings-endpoints/get-private-settings.md) |
| `/api/v1/settings.public` | `GET` | Lists all public settings. | [Link](settings-endpoints/get-public-settings.md) |
| `/api/v1/settings.oauth` | `GET` | Return list of all available oauth services. | [Link](settings-endpoints/get-all-oauth.md) |
| `/api/v1/service.configurations` | `GET` | Lists all service configurations. | [Link](settings-endpoints/get-service-configurations.md) |
| `/api/v1/settings/:_id` | `GET` | Gets a setting. | [Link](settings-endpoints/get-settings-by-id.md) |
| `/api/v1/settings/:_id` | `POST` | Updates a setting. | [Link](settings-endpoints/update-settings.md) |

## **Stats** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/statistics` | ​get | Document Under Development |
| ​`/api/v1/statistics.list` | ​get | Document Under Development |

## **Subscriptions** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/subscriptions.get` | Get all subscriptions. | [Link](subscriptions-endpoints/get-all-subscriptions.md) |
| `/api/v1/subscriptions.getOne` | Get the subscription by room Id. | [Link](subscriptions-endpoints/get-subscription-room.md) |
| `/api/v1/subscriptions.read` | Mark a room as read. | [Link](subscriptions-endpoints/mark-channel-as-read.md) |
| `/api/v1/subscriptions.unread` | Mark messages as unread. | [Link](subscriptions-endpoints/mark-messages-as-unread.md) |

## **Teams** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/teams.list` | Lists the public and private teams the caller is part of. | [Link](teams-endpoints/list-of-teams-of-caller.md) |
| `/api/v1/teams.listAll` | Lists all of the teams and their information. | [Link](teams-endpoints/list-all-teams-with-info.md) |
| `/api/v1/teams.create` | Creates a new team. | [Link](teams-endpoints/create-a-new-team.md) |
| `/api/v1/teams.convertToChannel` | post | Document Under Development |
| `/api/v1/teams.addRooms` | Adds rooms to the team. | [Link](teams-endpoints/add-rooms-to-a-team.md) |
| `/api/v1/teams.removeRoom` | Removes a room from a team. | [Link](teams-endpoints/remove-a-room-from-team.md) |
| `/api/v1/teams.updateRoom` | Updates a room from a team, limited to permissions. | [Link](teams-endpoints/update-room-from-a-team.md) |
| `/api/v1/teams.listRooms` | Lists all rooms of the team. | [Link](teams-endpoints/list-rooms-of-a-team.md) |
| `/api/v1/teams.listRoomsOfUser` | Lists only the team's rooms the user has joined. | [Link](teams-endpoints/list-rooms-of-user-of-a-team.md) |
| `/api/v1/teams.members` | Retrieves all team members. | [Link](teams-endpoints/get-teams-members.md) |
| `/api/v1/teams.addMembers` | Adds members to the team. | [Link](teams-endpoints/add-members.md) |
| `/api/v1/teams.updateMember` | Updates a team member's roles, limited to permissions. | [Link](teams-endpoints/update-a-teams-member.md) |
| `/api/v1/teams.removeMember` | Removes a member from a team. | [Link](teams-endpoints/remove-member-from-team.md) |
| `/api/v1/teams.leave` | Leaves a team. | [Link](teams-endpoints/leave-a-team.md) |
| `/api/v1/teams.info` | Gets a team's information. | [Link](teams-endpoints/get-teams-info.md) |
| `/api/v1/teams.delete` | Removes a team. | [Link](teams-endpoints/delete-a-team.md) |
| `/api/v1/teams.autocomplete` | Lists the teams whose names match a given pattern. | [Link](teams-endpoints/autocomplete-team.md) |
| `/api/v1/teams.update` | Updates an existing team \(name and type\). | [Link](teams-endpoints/update-a-team.md) |

## **Users** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Method | Short Description | Details Page |
| :--- | :--- | :--- | :--- |
| ​`/api/v1/users.create` | `​Post` | Create a new user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-user-endpoint) |
| ​`/api/v1/users.delete` | ​`Post` | Deletes an existing user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/delete) |
| ​`/api/v1/users.deleteOwnAccount` | `Post` | Deletes your own user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/deleteownaccount) |
| `​/api/v1/users.getAvatar` | `Get` | Gets the URL for a user’s avatar. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getavatar) |
| `​/api/v1/users.setActiveStatus` | `Post` | Set user's active status | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-users-status-active) |
| `​/api/v1/users.deactivateIdle` | `Post` | Deactivate Idle users | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/deactivate-idle-users) |
| `​/api/v1/users.getPresence` | `Get` | Gets a user's presence  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-presence) |
| `​/api/v1/users.info` | `Get` | Retrieves information about a user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-info) |
| `​/api/v1/users.list` | `Get` | Get all of the users in the system and their information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-list) |
| `​/api/v1/users.register` | `Post` | Register users | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/register-users) |
| `​/api/v1/users.resetAvatar` | `Post` | Reset avatar | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/reset-avatar) |
| `​/api/v1/users.setAvatar` | `Post` | Set avatar | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-avatar) |
| `​/api/v1/users.getStatus` | `Get` | Gets a user's status  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-status) |
| `​/api/v1/users.setStatus` | `Post` | Sets a user status | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-status) |
| `​/api/v1/users.update` | `Post` | Update user | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/update-user) |
| `​/api/v1/users.updateOwnBasicInfo` | `Post` | Update own basic information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/update-own-basic-information) |
| `​/api/v1/users.createToken` | `Post` | Create a user authentication token | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-users-token) |
| `​/api/v1/users.getPreferences` | `Get` | Gets all preferences of the user. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-user-preferences) |
| `​/api/v1/users.setPreferences` | `Post` | Sets preferences of the user. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-preferences) |
| `​/api/v1/users.forgotPassword` | `Post` | Send `an` email to reset your password. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/forgotpassword) |
| `​/api/v1/users.getUsernameSuggestion` | `Get` | Suggestion of new username to user. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getusernamesuggestion) |
| `​/api/v1/users.generatePersonalAccessToken` | `Post` | Generate Personal Access Token | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/generatepersonalaccesstoken) |
| `​/api/v1/users.regeneratePersonalAccessToken` | `Post` | Regenerate a user's personal access token | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/regeneratepersonalaccesstoken) |
| `​/api/v1/users.getPersonalAccessTokens` | `Get` | Gets the user’s personal access tokens | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getpersonalaccesstokens) |
| `​/api/v1/users.removePersonalAccessToken` | `Post` | Remove a personal access token | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/removepersonalaccesstoken) |
| `​/api/v1/users.2fa.enableEmail` | `Post` |  | Document Under Development  |
| `​/api/v1/users.2fa.disableEmail` | `Post` |  | Document Under Development  |
| `​/api/v1/users.2fa.sendEmailCode` | `post` |  | Document Under Development  |
| `​/api/v1/users.presence` | `Get` | Gets all connected users presence. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/presence) |
| `​/api/v1/users.requestDataDownload` | `Get` | Request the user's data for download. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/requestdatadownload)  |
| `​/api/v1/users.logoutOtherClients` | `Post` |  | Document Under Development  |
| `​/api/v1/users.autocomplete` | `Get` |  | Document Under Development  |
| `​/api/v1/users.removeOtherTokens` | `Post` | Remove other tokens | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/remove-other-tokens) |
| `​/api/v1/users.resetE2EKey` | `post` |  | Document Under Development |
| `​/api/v1/users.resetTOTP` | `post` |  | Document Under Development |
| `​/api/v1/users.listTeams` | `get` |  | Document Under Development |
| `​/api/v1/users.logout` | post |  | Document Under Development |

## **Video Conference** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/video-conference/jitsi.update-timeout` | ​Updates the timeout of Jitsi video conference in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout) |

## **Webdav** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/webdav.getMyAccounts` | ​Retrieves the user's webdav accounts | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts) |

