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
| `/api/v1/banners.getNew` | Get  | Link |
| `/api/v1/banners.dismiss` | Post | Link |

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
| `/api/v1/channels.convertToTeam` | post |  |

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
| `/api/v1/chat.ignoreUser` | Ignores an user from a chat. | [Link](chat-endpoints/ignoreuser.md) |
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
| `/api/v1/chat.syncMessages` | get |  |

## Cloud Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/cloud.manualRegister` | Post | Link |

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
| `/api/v1/custom-user-status.create` | post |  |
| `/api/v1/custom-user-status.delete` | post |  |
| `/api/v1/custom-user-status.update` | post |  |

## DNS Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/`dns.resolve.srv | get | Link |
| `/api/v1/`dns.resolve.txt | post | Link |

## E2E Endpoints



| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/`e2e.fetchMyKeys | get | Link |
| `/api/v1/`e2e.getUsersOfRoomWithoutKey | post | Link |
| `/api/v1/`e2e.setRoomKeyID | post |  |
| `/api/v1/`e2e.setUserPublicAndPrivateKeys | post |  |
| `/api/v1/`e2e.updateGroupKey | post |  |



## Email Inbox Endpoints

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/` |  | Link |
| `/api/v1/` |  | Link |

## Custom Emojis Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## Groups Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## IM Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## Imports Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Instances** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Integrations** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Invites** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Misc** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Oauth apps** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Permissions** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Push** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Roles** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Rooms** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Settings** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Stats** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Subscriptions** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/` | ​Content | Link |
| ​`/api/v1/` | ​Content | Link |

## **Teams** Endpoints <a id="email-inbox-endpoints"></a>

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/teams.list` | Lists the public and private teams the caller is part of. | [Link](teams-endpoints/teams-list-of-caller.md) |
| `/api/v1/teams.listAll` | Lists all of the teams and their information. | [Link](teams-endpoints/list-all-teams-with-info.md) |
| `/api/v1/teams.create` | Creates a new team. | [Link](teams-endpoints/create-a-new-team.md) |
| `/api/v1/teams.convertToChannel` | post |  |
| `/api/v1/teams.addRooms` | Adds rooms to the team. | [Link](teams-endpoints/add-rooms.md) |
| `/api/v1/teams.removeRoom` | Removes a room from a team. | [Link](teams-endpoints/remove-room.md) |
| `/api/v1/teams.updateRoom` | Updates a room from a team, limited to permissions. | [Link](teams-endpoints/update-room.md) |
| `/api/v1/teams.listRooms` | Lists all rooms of the team. | [Link](teams-endpoints/list-rooms.md) |
| `/api/v1/teams.listRoomsOfUser` | Lists only the team's rooms the user has joined. | [Link](teams-endpoints/list-rooms-of-user.md) |
| `/api/v1/teams.members` | Retrieves all team members. | [Link](teams-endpoints/members.md) |
| `/api/v1/teams.addMembers` | Adds members to the team. | [Link](teams-endpoints/add-members.md) |
| `/api/v1/teams.updateMember` | Updates a team member's roles, limited to permissions. | [Link](teams-endpoints/update-member.md) |
| `/api/v1/teams.removeMember` | Removes a member from a team. | [Link](teams-endpoints/remove-member.md) |
| `/api/v1/teams.leave` | Leaves a team. | [Link](teams-endpoints/leave.md) |
| `/api/v1/teams.info` | Gets a team's information. | [Link](teams-endpoints/info.md) |
| `/api/v1/teams.delete` | Removes a team. | [Link](teams-endpoints/delete.md) |
| `/api/v1/teams.autocomplete` | Lists the teams whose names match a given pattern. | [Link](teams-endpoints/autocomplete.md) |
| `/api/v1/teams.update` | Updates an existing team \(name and type\). | [Link](teams-endpoints/update.md) |

## **Users** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/users.create` | ​post | Link |
| ​`/api/v1/users.delete` | ​post | Link |
| ​`/api/v1/users.deleteOwnAccount` | `post` | `Link` |
| `​/api/v1/users.getAvatar` | `get` | `Link` |
| `​/api/v1/users.setActiveStatus` | `post` | `Link` |
| `​/api/v1/users.deactivateIdle` | `post` | `Link` |
| `​/api/v1/users.getPresence` | `get` | `Link` |
| `​/api/v1/users.info` | `get` | `Link` |
| `​/api/v1/users.list` | `get` | `Link` |
| `​/api/v1/users.register` | `get` | `Link` |
| `​/api/v1/users.resetAvatar` | `post` | `Link` |
| `​/api/v1/users.setAvatar` | `post` | `Link` |
| `​/api/v1/users.getStatus` | `get` | `Link` |
| `​/api/v1/users.setStatus` | `post` | `Link` |
| `​/api/v1/users.update` | `post` | `Link` |
| `​/api/v1/users.updateOwnBasicInfo` | `post` | `Link` |
| `​/api/v1/users.createToken` | `post` | `Link` |
| `​/api/v1/users.getPreferences` | `get` | `Link` |
| `​/api/v1/users.setPreferences` | `post` | `Link` |
| `​/api/v1/users.forgotPassword` | `post` | `Link` |
| `​/api/v1/users.getUsernameSuggestion` | `get` | `Link` |
| `​/api/v1/users.generatePersonalAccessToken` | `post` | `Link` |
| `​/api/v1/users.regeneratePersonalAccessToken` | `post` | `Link` |
| `​/api/v1/users.getPersonalAccessTokens` | `get` | `Link` |
| `​/api/v1/users.removePersonalAccessToken` | `post` | `Link` |
| `​/api/v1/users.2fa.enableEmail` | `post` | `Link` |
| `​/api/v1/users.2fa.disableEmail` | `post` | `Link` |
| `​/api/v1/users.2fa.sendEmailCode` | `post` | `Link` |
| `​/api/v1/users.presence` | Gets all connected users presence. | `Link` |
| `​/api/v1/users.requestDataDownload` | `get` | `Link` |
| `​/api/v1/users.logoutOtherClients` | `post` | `Link` |
| `​/api/v1/users.autocomplete` | `get` | `Link` |
| `​/api/v1/users.removeOtherTokens` | `post` | `Link` |
| `​/api/v1/users.resetE2EKey` | `post` | `Link` |
| `​/api/v1/users.resetTOTP` | `post` | `Link` |
| `​/api/v1/users.listTeams` | `get` | `Link` |
| `​/api/v1/users.logout` | post | `Link` |

## **Video Conference** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| ​`/api/v1/video-conference/jitsi.update-timeout` | ​Updates the timeout of Jitsi video conference in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout) |

## **Webdav** Endpoints <a id="email-inbox-endpoints"></a>

| URL | Short Description | Details Page |
| :--- | :--- | :--- |
| `/api/v1/webdav.getMyAccounts` | ​Retrieves the user's webdav accounts | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts) |

