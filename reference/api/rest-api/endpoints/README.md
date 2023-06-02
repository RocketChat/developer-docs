# Endpoints

#### [Access Tokens](other-important-endpoints/access-tokens-endpoints.md)

#### [Pagination](other-important-endpoints/offset-and-count-and-sort-info.md)

#### [Query and Fields](other-important-endpoints/query-and-fields-info.md)

#### [Rate Limiter Endpoints](other-important-endpoints/rate-limiter-endpoints.md)

#### [Avatars](../avatars.md)

#### [Authentication](other-important-endpoints/authentication-endpoints/)

#### [Two Factor Authentication](../../realtime-api/2fa.md)

## Assets&#x20;

<table><thead><tr><th>URL</th><th width="290.3333333333333">Short Description</th><th>Details Page</th></tr></thead><tbody><tr><td><code>/api/v1/assets.setAsset</code></td><td>Sets an asset image by name.</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset">Link</a></td></tr><tr><td><code>/api/v1/assets.unsetAsset</code></td><td>Unsets an asset by name.</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset">Link</a></td></tr></tbody></table>

## Auto Translate&#x20;

| URL                                           | Short Description                               | Details Page                                                                                                        |
| --------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/autotranslate.getSupportedLanguages` | Gets the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings`          | Saves some settings about auto-translate.       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings)          |
| `/api/v1/autotranslate.translateMessage`      | Translates the message.                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage)      |

## Banners&#x20;

| URL                       | Short Description                                      | Details Page                                                                                                                 |
| ------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/banners/:id`     | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banner-by-id) |
| `/api/v1/banners`         | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banners)      |
| `/api/v1/banners.dismiss` | Dismisses a banner                                     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/dismiss-a-banner) |

## Channels

These methods apply to public channels only. Use `groups.*` methods for private channels.

| URL                                            | Short Description                                             | Details Page                                                                                                                         |
| ---------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `/api/v1/channels.addAll`                      | Adds all of the users on the server to a channel.             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addall)                                      |
| `/api/v1/channels.addLeader`                   | Gives the role of Leader for a user in the current channel.   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addleader)                                   |
| `/api/v1/channels.addModerator`                | Gives the role of moderator to a user in a channel.           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addmoderator)                                |
| `/api/v1/channels.addOwner`                    | Gives the role of owner to a user in a channel.               | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/addowner)                                    |
| `/api/v1/channels.anonymousread`               | Gets the messages in public channels to an anonymous user     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/anonymousread)                               |
| `/api/v1/channels.archive`                     | Archives a channel.                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/archive)                                     |
| `/api/v1/channels.close`                       | Removes a channel from a user's list of channels.             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/close)                                       |
| `/api/v1/channels.counters`                    | Retrieves channel counters.                                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/counters)                                    |
| `/api/v1/channels.create`                      | Creates a new channel.                                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/create)                                      |
| `/api/v1/channels.delete`                      | Removes a channel.                                            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/delete)                                      |
| `/api/v1/channels.getAllUserMentionsByChannel` | Retrieves all the mentions of a channel.                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/getallusermentionsbychannel)                 |
| `/api/v1/channels.files`                       | Retrieves a list of files from a channel.                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/files)                                       |
| `/api/v1/channels.getIntegrations`             | Retrieves the channel's integration.                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/getintegrations)                             |
| `/api/v1/channels.history`                     | Retrieves the messages from a channel.                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/history)                                     |
| `/api/v1/channels.info`                        | Gets a channel's information.                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/info)                                        |
| `/api/v1/channels.invite`                      | Adds a user to a channel.                                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/invite)                                      |
| `/api/v1/channels.join`                        | Joins yourself to a channel.                                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/join)                                        |
| `/api/v1/channels.kick`                        | Removes a user from a channel.                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/kick)                                        |
| `/api/v1/channels.leave`                       | Removes the calling user from a channel.                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/leave)                                       |
| `/api/v1/channels.list`                        | Retrieves all of the channels from the server.                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/list)                                        |
| `/api/v1/channels.list.joined`                 | Retrieves only the channels the calling user has joined.      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/list-joined)                                 |
| `/api/v1/channels.members`                     | Retrieves all channel users.                                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/members)                                     |
| `/api/v1/channels.messages`                    | Retrieves all channel messages.                               | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/messages)                                    |
| `/api/v1/channels.moderators`                  | Lists all moderators of a channel.                            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/moderators)                                  |
| `/api/v1/channels.online`                      | Lists all online users of a channel.                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/online)                                      |
| `/api/v1/channels.open`                        | Adds the channel back to the user's list of channels.         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/open)                                        |
| `/api/v1/channels.removeleader`                | Removes the role of Leader for a user in the current channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/channels/removeleader)                                |
| `/api/v1/channels.removeModerator`             | Removes the role of moderator from a user in a channel.       | [Link](core-endpoints/channels-endpoints/removemoderator.md)                                                                         |
| `/api/v1/channels.removeOwner`                 | Removes the role of the owner from a user in a channel.       | [Link](core-endpoints/channels-endpoints/removeowner.md)                                                                             |
| `/api/v1/channels.rename`                      | Changes a channel's name.                                     | [Link](core-endpoints/channels-endpoints/rename.md)                                                                                  |
| `/api/v1/channels.roles`                       | Gets the user's roles in the channel.                         | [Link](core-endpoints/channels-endpoints/roles.md)                                                                                   |
| `/api/v1/channels.setAnnouncement`             | Sets a channel's announcement.                                | [Link](core-endpoints/channels-endpoints/setannouncement.md)                                                                         |
| `/api/v1/channels.setCustomFields`             | Sets a channel's custom fields.                               | [Link](core-endpoints/channels-endpoints/setcustomfields.md)                                                                         |
| `/api/v1/channels.setDefault`                  | Sets a channel's default status.                              | [Link](core-endpoints/channels-endpoints/setdefault.md)                                                                              |
| `/api/v1/channels.setDescription`              | Sets a channel's description.                                 | [Link](core-endpoints/channels-endpoints/setdescription.md)                                                                          |
| `/api/v1/channels.setJoinCode`                 | Sets the channel's code required to join it.                  | [Link](core-endpoints/channels-endpoints/setjoincode.md)                                                                             |
| `/api/v1/channels.setPurpose`                  | Sets a channel's description.                                 | [Link](core-endpoints/channels-endpoints/setpurpose.md)                                                                              |
| `/api/v1/channels.setReadOnly`                 | Sets whether a channel is read-only or not.                   | [Link](core-endpoints/channels-endpoints/setreadonly.md)                                                                             |
| `/api/v1/channels.setTopic`                    | Sets a channel's topic.                                       | [Link](core-endpoints/channels-endpoints/settopic.md)                                                                                |
| `/api/v1/channels.setType`                     | Sets the type of room the channel should be.                  | [Link](core-endpoints/channels-endpoints/settype.md)                                                                                 |
| `/api/v1/channels.unarchive`                   | Unarchives a channel.                                         | [Link](core-endpoints/channels-endpoints/unarchive.md)                                                                               |
| `/api/v1/channels.convertToTeam`               | Converts channel to team                                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/channels-endpoints/convert-channel-to-team) |

## Chat&#x20;

| URL                                    | Short Description                                                | Details Page                                                                                                                     |
| -------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/chat.delete`                  | Deletes an existing chat message.                                | [Link](core-endpoints/chat-endpoints/delete.md)                                                                                  |
| `/api/v1/chat.followMessage`           | Follows an existing chat message.                                | [Link](core-endpoints/chat-endpoints/follow-message.md)                                                                          |
| `/api/v1/chat.getDeletedMessages`      | Retrieves the deleted messages from a specific date.             | [Link](core-endpoints/chat-endpoints/getdeletedmessages.md)                                                                      |
| `/api/v1/chat.getDiscussions`          | Retrieves the discussions of a room.                             | [Link](core-endpoints/chat-endpoints/getdiscussions.md)                                                                          |
| `/api/v1/chat.getMentionedMessages`    | Retrieves the mentioned messages.                                | [Link](core-endpoints/chat-endpoints/getmentionedmessages.md)                                                                    |
| `/api/v1/chat.getMessage`              | Retrieves a single chat message.                                 | [Link](core-endpoints/chat-endpoints/getmessage.md)                                                                              |
| `/api/v1/chat.getMessageReadReceipts`  | Retrieves message read receipts.                                 | [Link](core-endpoints/chat-endpoints/getmessagereadreceipts.md)                                                                  |
| `/api/v1/chat.getPinnedMessages`       | Retrieves pinned messages from a room.                           | [Link](core-endpoints/chat-endpoints/getpinnedmessages.md)                                                                       |
| `/api/v1/chat.getSnippetedMessages`    | Retrieves snippet messages.                                      | [Link](core-endpoints/chat-endpoints/getsnippetedmessages.md)                                                                    |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippet message by id.                                 | [Link](core-endpoints/chat-endpoints/getsnippetedmessagebyid.md)                                                                 |
| `/api/v1/chat.getStarredMessages`      | Retrieves the starred messages.                                  | [Link](core-endpoints/chat-endpoints/getstarredmessages.md)                                                                      |
| `/api/v1/chat.getThreadMessages`       | Retrieves thread's messages.                                     | [Link](core-endpoints/chat-endpoints/getthreadmessages.md)                                                                       |
| `/api/v1/chat.getThreadsList`          | Retrieves channel's threads.                                     | [Link](core-endpoints/chat-endpoints/getthreadslist.md)                                                                          |
| `/api/v1/chat.ignoreUser`              | Ignores abuser from a chat.                                      | [Link](core-endpoints/chat-endpoints/ignoreuser.md)                                                                              |
| `/api/v1/chat.pinMessage`              | Pins a chat message to the message's channel.                    | [Link](core-endpoints/chat-endpoints/pinmessage.md)                                                                              |
| `/api/v1/chat.postMessage`             | Posts a new chat message.                                        | [Link](core-endpoints/chat-endpoints/postmessage.md)                                                                             |
| `/api/v1/chat.react`                   | Sets/unsets the user's reaction to an existing chat message.     | [Link](core-endpoints/chat-endpoints/chat-message-reactions.md)                                                                  |
| `/api/v1/chat.reportMessage`           | Reports a message.                                               | [Link](core-endpoints/chat-endpoints/reportmessage.md)                                                                           |
| `/api/v1/chat.search`                  | Searches for messages in a channel.                              | [Link](core-endpoints/chat-endpoints/search-message.md)                                                                          |
| `/api/v1/chat.starMessage`             | Stars a chat message for the authenticated user.                 | [Link](core-endpoints/chat-endpoints/starmessage.md)                                                                             |
| `/api/v1/chat.sendMessage`             | Sends a new chat message.                                        | [Link](core-endpoints/chat-endpoints/send-message.md)                                                                            |
| `/api/v1/chat.syncThreadMessages`      | Retrieves synced thread's messages.                              | [Link](core-endpoints/chat-endpoints/syncthreadmessages.md)                                                                      |
| `/api/v1/chat.syncThreadsList`         | Retrieves thread's synced channel threads.                       | [Link](core-endpoints/chat-endpoints/syncthreadslist.md)                                                                         |
| `/api/v1/chat.unfollowMessage`         | Unfollows an existing chat message.                              | [Link](core-endpoints/chat-endpoints/unfollowmessage.md)                                                                         |
| `/api/v1/chat.unPinMessage`            | Removes the pinned status of the provided chat message.          | [Link](core-endpoints/chat-endpoints/unpinmessage.md)                                                                            |
| `/api/v1/chat.unStarMessage`           | Removes the star on the chat message for the authenticated user. | [Link](core-endpoints/chat-endpoints/unstarmessage.md)                                                                           |
| `/api/v1/chat.update`                  | Updates the text of the chat message.                            | [Link](core-endpoints/chat-endpoints/message-update.md)                                                                          |
| `/api/v1/chat.syncMessages`            | Syncs messages                                                   | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/chat-endpoints/sync-messages) |

## Cloud&#x20;

| URL                            | Short Description              | Details Page                                                                                                                              |
| ------------------------------ | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/cloud.manualRegister` | Manually registers a workspace | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/cloud-endpoints/cloud-manual-register) |

## Commands&#x20;

| URL                        | Short Description                                                         | Details Page                                                                                                                     |
| -------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/commands.get`     | Retrieves the specification of the slash command.                         | [Link](core-endpoints/commands-endpoints/get-slash-commands.md)                                                                  |
| `/api/v1/commands.list`    | Lists all available slash commands.                                       | [Link](core-endpoints/commands-endpoints/list.md)                                                                                |
| `/api/v1/commands.run`     | Executes a slash command in the specified room.                           | [Link](core-endpoints/commands-endpoints/execute-a-slash-command.md)                                                             |
| `/api/v1/commands.preview` | Retrieves the preview data for the command and executes the preview item. | [Link](core-endpoints/commands-endpoints/preview.md)                                                                             |
| `/api/v1/commands.preview` | Executes command's preview item                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/commands/execute-commands-preview-item) |

## Custom Sounds&#x20;

| URL                          | Short Description                  | Details Page                                                                                                                                                     |
| ---------------------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | [Link](https://app.gitbook.com/@rocket-chat/s/rocket-chat-developer/\~/drafts/-MgSmy428hAP1znS6g3V/api/rest-api/endpoints/team-collaboration/custom-sounds/list) |

## Custom User Status&#x20;

| URL                                 | Short Description                         | Details Page                                                                                                                                                    |
| ----------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-user-status.list`   | Lists all available custom user's status. | [Link](core-endpoints/custom-user-status-endpoints/list.md)                                                                                                     |
| `/api/v1/custom-user-status.create` | Creates custom user status                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/create-custom-user-status)      |
| `/api/v1/custom-user-status.delete` | Deletes a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/delete-custom-user-status)      |
| `/api/v1/custom-user-status.update` | Updates a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/update-custom-user-status-type) |

## DNS&#x20;

| URL                       | Short Description                                      | Details Page                                                                                                                      |
| ------------------------- | ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/dns.resolve.srv` | get                                                    | Document Under Development                                                                                                        |
| `/api/v1/dns.resolve.txt` | Resolves DNS text records (TXT records) for a hostname | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/dns-endpoints/dns-resolve-txt) |

## E2E&#x20;

| URL                                       | Short Description                                               | Details Page                                                                                                                                        |
| ----------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/e2e.fetchMyKeys`                 | Retrieves E2E keys of logged in user                            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/fetch-your-e2e-keys)               |
| `/api/v1/e2e.getUsersOfRoomWithoutKey`    | Retrieves Users Of Room Without E2E Key                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/get-users-of-room-without-e2e-key) |
| `/api/v1/e2e.setRoomKeyID`                | Sets the end-to-end encryption key ID for a room                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-room-e2e-key)                  |
| `/api/v1/e2e.setUserPublicAndPrivateKeys` | Sets the end-to-end encryption keys for the authenticated user. | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-users-key)                     |
| `/api/v1/e2e.updateGroupKey`              | Updates the end-to-end encryption key for a user in a room.     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/update-user-e2e-key-in-room)       |

## Email Inbox&#x20;

| URL                                  | Short Description                    | Details Page                                                                                                                                             |
| ------------------------------------ | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/email-inbox.list`           | Retrieves mail Inbox list            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-list)               |
| `/api/v1/email-inbox`                | Sets the email inbox for your server | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/set-email-inbox)                |
| `/api/v1/email-inbox/:_id`           | Retrieves email Inbox by id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-by-id)              |
| `/api/v1/email-inbox/:_id`           | Delete email inbox using id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/delete-email-inbox-by-id)       |
| `/api/v1/email-inbox.search`         | Searches email inbox by address      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/search-email-inbox-by-email)    |
| `/api/v1/email-inbox.send-test/:_id` | Sends test email to email inbox      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/send-test-email-to-email-inbox) |

## Custom Emoji <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                           | Short Description                          | Details Page                                                                                                                                      |
| ----------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/emoji-custom.all`    | Retrieves all custom emojis                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-emoji-endpoints/list-all-custom-emojis) |
| `/api/v1/emoji-custom.list`   | Retrieves an updated list of custom emojis | [Link](core-endpoints/custom-emoji-endpoints/list-custom-emojis.md)                                                                               |
| `/api/v1/emoji-custom.create` | Creates new custom emoji.                  | [Link](core-endpoints/custom-emoji-endpoints/create-new-custom-emoji.md)                                                                          |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji.           | [Link](core-endpoints/custom-emoji-endpoints/delete-custom-emoji.md)                                                                              |
| `/api/v1/emoji-custom.update` | Updates an existent custom emoji.          | [Link](core-endpoints/custom-emoji-endpoints/update-a-custom-emoji.md)                                                                            |

## Group  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                              | Short Description                                           | Details Page                                                                                                                             |
| -------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/groups.addAll`          | Adds all of the users on the server to a private group.     | [Link](core-endpoints/groups-endpoints/addall.md)                                                                                        |
| `/api/v1/groups.addLeader`       | Gives the role of Leader for a user in the current group.   | [Link](core-endpoints/groups-endpoints/addleader.md)                                                                                     |
| `/api/v1/groups.addModerator`    | Gives the role of moderator to a user in a group.           | [Link](core-endpoints/groups-endpoints/addmoderator.md)                                                                                  |
| `/api/v1/groups.addOwner`        | Gives the role of owner to a user in a group.               | [Link](core-endpoints/groups-endpoints/addowner.md)                                                                                      |
| `/api/v1/groups.archive`         | Archives a private group.                                   | [Link](core-endpoints/groups-endpoints/archive.md)                                                                                       |
| `/api/v1/groups.close`           | Removes a private group from the list of groups.            | [Link](core-endpoints/groups-endpoints/close.md)                                                                                         |
| `/api/v1/groups.counters`        | Retrieves group counters.                                   | [Link](core-endpoints/groups-endpoints/counters.md)                                                                                      |
| `/api/v1/groups.create`          | Creates a new private group.                                | [Link](core-endpoints/groups-endpoints/create.md)                                                                                        |
| `/api/v1/groups.delete`          | Removes a private group.                                    | [Link](core-endpoints/groups-endpoints/delete.md)                                                                                        |
| `/api/v1/groups.files`           | Retrieves a list of files from a private group.             | [Link](core-endpoints/groups-endpoints/files.md)                                                                                         |
| `/api/v1/groups.getIntegrations` | Retrieves the integrations assigned to the group.           | [Link](core-endpoints/groups-endpoints/getintegrations.md)                                                                               |
| `/api/v1/groups.history`         | Retrieves the messages from a private group.                | [Link](core-endpoints/groups-endpoints/history.md)                                                                                       |
| `/api/v1/groups.info`            | Retrieves the information about a private group.            | [Link](core-endpoints/groups-endpoints/info.md)                                                                                          |
| `/api/v1/groups.invite`          | Adds a user to the private group.                           | [Link](team-collaboration-endpoints/groups-endpoints/invite.md)                                                                          |
| `/api/v1/groups.kick`            | Removes a user from a private group.                        | [Link](core-endpoints/groups-endpoints/kick.md)                                                                                          |
| `/api/v1/groups.leave`           | Removes the calling user from the private group.            | [Link](core-endpoints/groups-endpoints/leave.md)                                                                                         |
| `/api/v1/groups.list`            | Lists the private groups the caller is part of.             | [Link](core-endpoints/groups-endpoints/list.md)                                                                                          |
| `/api/v1/groups.listAll`         | Lists all the private groups.                               | [Link](core-endpoints/groups-endpoints/listall.md)                                                                                       |
| `/api/v1/groups.moderators`      | Lists all moderators of a group.                            | [Link](core-endpoints/groups-endpoints/moderators.md)                                                                                    |
| `/api/v1/groups.members`         | Retrieves the users of participants of a private group.     | [Link](core-endpoints/groups-endpoints/members.md)                                                                                       |
| `/api/v1/groups.messages`        | Retrieves all group messages.                               | [Link](core-endpoints/groups-endpoints/messages.md)                                                                                      |
| `/api/v1/groups.online`          | Lists all online users of a group.                          | [Link](https://github.com/RocketChat/docs/tree/aeb4dd8de5017b7cd9c9d9367a0e2155f911ba5a/api/rest-api/methods/groups/online.md)           |
| `/api/v1/groups.open`            | Adds the private group back to the list of groups.          | [Link](core-endpoints/groups-endpoints/open.md)                                                                                          |
| `/api/v1/groups.removeLeader`    | Removes the role of Leader for a user in the current group. | [Link](core-endpoints/groups-endpoints/removeleader.md)                                                                                  |
| `/api/v1/groups.removeModerator` | Removes the role of moderator from a user in a group.       | [Link](core-endpoints/groups-endpoints/removemoderator.md)                                                                               |
| `/api/v1/groups.removeOwner`     | Removes the role of owner from a user in a group.           | [Link](core-endpoints/groups-endpoints/removeowner.md)                                                                                   |
| `/api/v1/groups.rename`          | Changes the name of the private group.                      | [Link](core-endpoints/groups-endpoints/rename.md)                                                                                        |
| `/api/v1/groups.roles`           | Retrieves the user's roles in the private group.            | [Link](core-endpoints/groups-endpoints/roles.md)                                                                                         |
| `/api/v1/groups.setAnnouncement` | Sets a group's announcement.                                | [Link](core-endpoints/groups-endpoints/setannouncement.md)                                                                               |
| `/api/v1/groups.setCustomFields` | Sets private group's custom fields.                         | [Link](core-endpoints/groups-endpoints/setcustomfields.md)                                                                               |
| `/api/v1/groups.setDescription`  | Sets a private group's description.                         | [Link](core-endpoints/groups-endpoints/setdescription.md)                                                                                |
| `/api/v1/groups.setPurpose`      | Sets a private group's description.                         | [Link](core-endpoints/groups-endpoints/setpurpose.md)                                                                                    |
| `/api/v1/groups.setReadOnly`     | Sets whether the room is read-only or not.                  | [Link](core-endpoints/groups-endpoints/setreadonly.md)                                                                                   |
| `/api/v1/groups.setTopic`        | Sets a private group's topic.                               | [Link](core-endpoints/groups-endpoints/settopic.md)                                                                                      |
| `/api/v1/groups.setType`         | Sets the type of room this group will be.                   | [Link](core-endpoints/groups-endpoints/settype.md)                                                                                       |
| `/api/v1/groups.unarchive`       | Unarchives a private group.                                 | [Link](core-endpoints/groups-endpoints/unarchive.md)                                                                                     |
| `/api/v1/groups.setEncrypted`    | Sets the encryption for a group                             | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/groups-endpoints/group-set-encrypted) |
| `/api/v1/groups.convertToTeam`   | Convert a private group to a team                           | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/groups-endpoints/group-converttoteam) |

## DM/IM <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                          | Short Description                                             | Details Page                                                                                                            |
| ---------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/im.delete`          | Removes a direct message session                              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/im-endpoints/delete) |
| `/api/v1/im.close`           | Removes a direct message from the list of direct messages.    | [Link](core-endpoints/im-endpoints/close.md)                                                                            |
| `/api/v1/im.counters`        | Gets counters of direct messages.                             | [Link](core-endpoints/im-endpoints/counters.md)                                                                         |
| `/api/v1/im.create`          | Creates a direct message session with another user.           | [Link](core-endpoints/im-endpoints/create.md)                                                                           |
| `/api/v1/im.history`         | Retrieves the messages from a direct message.                 | [Link](core-endpoints/im-endpoints/history.md)                                                                          |
| `/api/v1/im.files`           | Retrieves a list of files from a direct message.              | [Link](core-endpoints/im-endpoints/files.md)                                                                            |
| `/api/v1/im.members`         | Retrieves the users of participants of a direct message.      | [Link](core-endpoints/im-endpoints/members.md)                                                                          |
| `/api/v1/im.messages`        | Retrieves the messages from the specific direct messages.     | [Link](core-endpoints/im-endpoints/messages.md)                                                                         |
| `/api/v1/im.messages.others` | Retrieves the messages from any direct message in the server. | [Link](core-endpoints/im-endpoints/messages-others.md)                                                                  |
| `/api/v1/im.list`            | Lists the direct messages the caller is part of.              | [Link](core-endpoints/im-endpoints/list.md)                                                                             |
| `/api/v1/im.list.everyone`   | Lists all direct messages to the caller in the server.        | [Link](core-endpoints/im-endpoints/list-everyone.md)                                                                    |
| `/api/v1/im.open`            | Adds the direct message back to the list of direct messages.  | [Link](core-endpoints/im-endpoints/open.md)                                                                             |
| `/api/v1/im.setTopic`        | Sets a direct message topic.                                  | [Link](core-endpoints/im-endpoints/settopic.md)                                                                         |

{% hint style="info" %}
From version 0.50.0 and on, you can call the methods using `dm` instead of `im`.
{% endhint %}

## Imports  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                                 | Short Description              | Details Page                                                                                                                                       |
| ----------------------------------- | ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/uploadImportFile`          | `Content`                      | Document Under Development                                                                                                                         |
| `/api/v1/downloadPublicImportFile`  | `Content`                      | Document Under Development                                                                                                                         |
| `/api/v1/startImport`               | `Content`                      | Document Under Development                                                                                                                         |
| `/api/v1/getImportFileData`         | Get file data of an upload.    | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/get-import-file-data)          |
| `/api/v1/getImportProgress`         | Get the progress of an import. | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/get-import-progress)           |
| `/api/v1/getLatestImportOperations` | Get latest import operations   | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/get-latest-import-operations)  |
| `/api/v1/downloadPendingFiles`      | Download pending files         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/download-pending-files)        |
| `/api/v1/downloadPendingAvata`      | Download pending avatars       | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/download-pending-avatars)      |
| `/api/v1/getCurrentImportOperation` | Gets current import operations | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/import-endpoints/get-current-import-operations) |

## Instances  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                     | Short Description   | Details Page                                                                                                                          |
| ----------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/instances.get` | Retrieves instances | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/instances-endpoints/get-instances) |

## **Integration** <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                            | Short Description                               | Details Page                                            |
| ------------------------------ | ----------------------------------------------- | ------------------------------------------------------- |
| `/api/v1/integrations.create`  | Creates an integration.                         | [Link](core-endpoints/integration-endpoints/create.md)  |
| `/api/v1/integrations.get`     | Gets an integration.                            | [Link](core-endpoints/integration-endpoints/get.md)     |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](core-endpoints/integration-endpoints/history.md) |
| `/api/v1/integrations.list`    | Lists all of the integrations.                  | [Link](core-endpoints/integration-endpoints/list.md)    |
| `/api/v1/integrations.remove`  | Removes an integration.                         | [Link](core-endpoints/integration-endpoints/remove.md)  |
| `/api/v1/integrations.update`  | Updates an integration.                         | [Link](core-endpoints/integration-endpoints/update.md)  |

## Invite

| Url                           | Short Description                                                         | Details Page                                                                                                                             |
| ----------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/findOrCreateInvite`  | Created a new Invite or returns an existing one with the same parameters. | [Link](core-endpoints/invite-endpoints/findorcreateinvite.md)                                                                            |
| `/api/v1/listInvites`         | Lists all of the invite tokens.                                           | [Link](core-endpoints/invite-endpoints/listinvites.md)                                                                                   |
| `/api/v1/removeInvite/:_id`   | Deletes an invite from the server.                                        | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/invite-endpoints/delete-invite-by-id) |
| `/api/v1/useInviteToken`      | Reports to the server that an invite token was used.                      | [Link](core-endpoints/invite-endpoints/report-use-invite-token.md)                                                                       |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid.                                       | [Link](core-endpoints/invite-endpoints/validateinvitetoken.md)                                                                           |

## LDAP  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

<table><thead><tr><th>Url</th><th width="198">Short Description</th><th>Details Page</th></tr></thead><tbody><tr><td><code>/api/v1/ldap.syncNow</code></td><td>LDAP SyncNow</td><td><a href="ldap-endpoints/ldap-syncnow.md">Link</a></td></tr></tbody></table>

## Misc <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

Just some generic information, such as information about the server and authenticated user.

| Url                    | Short Description                                                                | Details Page                                                                                                                                 |
| ---------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/directory`    | Searches by all users and channels available on server.                          | [Link](core-endpoints/miscellaneous-endpoints/directory.md)                                                                                  |
| `/api/v1/shield.svg`   | Gets the shield SVG (badge) to add in your website.                              | [Link](core-endpoints/miscellaneous-endpoints/shield-svg.md)                                                                                 |
| `/api/v1/spotlight`    | Searches for users or rooms that are visible to the user.                        | [Link](core-endpoints/miscellaneous-endpoints/spotlight.md)                                                                                  |
| `/api/v1/me`           | Gets user data of the authenticated user                                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/miscellaneous-endpoints/get-user-data)    |
| `/api/v1/stdout.queue` | Retrieves last 1000 lines of server logsRetrieves last 1000 lines of server logs | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/miscellaneous-endpoints/get-stdout-queue) |

## OAuth App <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

<table><thead><tr><th>Url</th><th width="198">Short Description</th><th>Details Page</th></tr></thead><tbody><tr><td><code>/api/v1/oauth-apps.get</code></td><td>Retrieves an OAuth App by id or client id.</td><td><a href="core-endpoints/oauthapps-endpoints/get.md">Link</a></td></tr><tr><td><code>/api/v1/oauth-apps.list</code></td><td>Retrieves a list of OAuth Apps.</td><td><a href="core-endpoints/oauthapps-endpoints/list.md">Link</a></td></tr></tbody></table>

## Permissions

| Url                           | Short Description                | Details Page                                                         |
| ----------------------------- | -------------------------------- | -------------------------------------------------------------------- |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](core-endpoints/permissions-endpoints/list-all-permissions.md) |
| `/api/v1/permissions.update`  | Edits permissions on the server. | [Link](core-endpoints/permissions-endpoints/update-permissions.md)   |

## Push <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                  | Short Description                   | Details Page                                                                                                                                       |
| -------------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/push.token` | Saves push token.                   | [Link](core-endpoints/push-token-endpoints/push-token.md)                                                                                          |
| `/api/v1/push.token` | Removes push token.                 | [Link](core-endpoints/push-token-endpoints/deletepushtoken.md)                                                                                     |
| `/api/v1/push.get`   | Get push notification for a message | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/push-token-endpoints/Get%20push%20notification) |

## Roles <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                                | Short Description                                                   | Details Page                                                                                                                              |
| ---------------------------------- | ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/roles.list`               | Lists all roles on the server.                                      | [Link](core-endpoints/roles-endpoints/list.md)                                                                                            |
| `/api/v1/roles.sync`               | Lists all roles on the server which are updated after a given date. | [Link](core-endpoints/roles-endpoints/sync.md)                                                                                            |
| `/api/v1/roles.create`             | Creates a new role.                                                 | [Link](core-endpoints/roles-endpoints/create.md)                                                                                          |
| `/api/v1/roles.addUserToRole`      | Edits permissions on the server.                                    | [Link](core-endpoints/roles-endpoints/addusertorole.md)                                                                                   |
| `/api/v1/roles.getUsersInRole`     | Retrieves the users that belong to a role.                          | [Link](core-endpoints/roles-endpoints/getusersinrole.md)                                                                                  |
| `/api/v1/roles.update`             | Updates an existing role in the system.                             | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/update.md) |
| `/api/v1/roles.delete`             | Deletes a role.                                                     | [Link](https://github.com/RocketChat/developer-docs/tree/a1d1fa7a40079462e8ee83df925258c15b84f653/api/rest-api/endpoints/roles/delete.md) |
| `/api/v1/roles.removeUserFromRole` | Unassigns a role from a user.                                       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/roles-endpoints/role-remove)                     |

## Rooms <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                                            | Short Description                                        | Details Page                                                                                                                                        |
| ---------------------------------------------- | -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/rooms.adminRooms`                     | Retrieves all rooms (requires special permission).       | [Link](core-endpoints/rooms-endpoints/adminrooms.md)                                                                                                |
| `/api/v1/rooms.cleanHistory`                   | Cleans up a room's history, requires special permission. | [Link](core-endpoints/rooms-endpoints/clean-room-history.md)                                                                                        |
| `/api/v1/rooms.createDiscussion`               | Creates a new discussion.                                | [Link](core-endpoints/rooms-endpoints/creatediscussion.md)                                                                                          |
| `/api/v1/rooms.favorite`                       | Favorites/Unfavorites room.                              | [Link](core-endpoints/rooms-endpoints/favorite-unfavourite-a-room.md)                                                                               |
| `/api/v1/rooms.get`                            | Retrieves rooms.                                         | [Link](core-endpoints/rooms-endpoints/get-rooms.md)                                                                                                 |
| `/api/v1/rooms.getDiscussions`                 | Retrieves room's discussions.                            | [Link](core-endpoints/rooms-endpoints/getdiscussions.md)                                                                                            |
| `/api/v1/rooms.info`                           | Gets info from a room.                                   | [Link](core-endpoints/rooms-endpoints/info.md)                                                                                                      |
| `/api/v1/rooms.leave`                          | Leaves a room.                                           | [Link](core-endpoints/rooms-endpoints/leave-room.md)                                                                                                |
| `/api/v1/rooms.saveNotification`               | Sets the notification settings of a specific channel.    | [Link](core-endpoints/rooms-endpoints/save-room-notification.md)                                                                                    |
| `/api/v1/rooms.upload/:rid`                    | Uploads a message with the attached file.                | [Link](core-endpoints/rooms-endpoints/upload-file-to-a-room.md)                                                                                     |
| `/api/v1/rooms.adminRooms.getRoom`             | Retrieves all admin rooms                                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/get-admin-rooms)                 |
| `/api/v1/rooms.autocomplete.channelAndPrivate` | Autocompletes private channel                            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/autocomplete-private-channel)    |
| `/api/v1/rooms.autocomplete.availableForTeams` | Autocompletes room name available for conversion to team | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/room-name-autocomplete-for-team) |
| `/api/v1/rooms.saveRoomSettings`               | Save the settings of a room                              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/save-room-settings)              |
| `/api/v1/rooms.changeArchivationState`         | Change the Archive state of a room.                      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/change-archivation-state)        |
| `/api/v1/rooms.export`                         | Export room to a file or email.                          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/rooms-endpoints/export-room)                     |

## Settings

You can get and update the settings via the REST API, only if you have permission to.

| Url                              | Short Description                             | Details Page                                                            |
| -------------------------------- | --------------------------------------------- | ----------------------------------------------------------------------- |
| `/api/v1/settings`               | Lists all private settings.                   | [Link](core-endpoints/settings-endpoints/get-private-settings.md)       |
| `/api/v1/settings.public`        | Lists all public settings.                    | [Link](core-endpoints/settings-endpoints/get-public-settings.md)        |
| `/api/v1/settings.oauth`         | Returns list of all available oauth services. | [Link](core-endpoints/settings-endpoints/get-all-oauth.md)              |
| `/api/v1/service.configurations` | Lists all service configurations.             | [Link](core-endpoints/settings-endpoints/get-service-configurations.md) |
| `/api/v1/settings/:_id`          | Retrieves a setting.                          | [Link](core-endpoints/settings-endpoints/get-setting-by-id.md)          |
| `/api/v1/settings/:_id`          | Updates a setting.                            | [Link](core-endpoints/settings-endpoints/update-setting.md)             |

## Stats <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                       | Short Description         | Details Page                                                                                                                            |
| ------------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/statistics`      | Retrieves statistics      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics)      |
| `/api/v1/statistics.list` | Retrieves statistics list | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics-list) |

## **Subscription**  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                            | Short Description                      | Details Page                                                              |
| ------------------------------ | -------------------------------------- | ------------------------------------------------------------------------- |
| `/api/v1/subscriptions.get`    | Retrieves all subscriptions.           | [Link](core-endpoints/subscriptions-endpoints/get-all-subscriptions.md)   |
| `/api/v1/subscriptions.getOne` | Retrieves the subscription by room Id. | [Link](core-endpoints/subscriptions-endpoints/get-subscription-room.md)   |
| `/api/v1/subscriptions.read`   | Marks a room as read.                  | [Link](core-endpoints/subscriptions-endpoints/mark-channel-as-read.md)    |
| `/api/v1/subscriptions.unread` | Marks messages as unread.              | [Link](core-endpoints/subscriptions-endpoints/mark-messages-as-unread.md) |

## Teams <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                              | Short Description                                         | Details Page                                                                                                                                |
| -------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/teams.list`             | Lists the public and private teams the caller is part of. | [Link](core-endpoints/teams-endpoints/list-of-teams-of-caller.md)                                                                           |
| `/api/v1/teams.listAll`          | Lists all of the teams and their information.             | [Link](core-endpoints/teams-endpoints/list-all-teams-with-info.md)                                                                          |
| `/api/v1/teams.create`           | Creates a new team.                                       | [Link](core-endpoints/teams-endpoints/create-a-new-team.md)                                                                                 |
| `/api/v1/teams.convertToChannel` | Converts team to channel.                                 | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/teams-endpoints/convert-team-to-channel) |
| `/api/v1/teams.addRooms`         | Adds rooms to the team.                                   | [Link](core-endpoints/teams-endpoints/add-rooms-to-a-team.md)                                                                               |
| `/api/v1/teams.removeRoom`       | Removes a room from a team.                               | [Link](core-endpoints/teams-endpoints/remove-a-room-from-team.md)                                                                           |
| `/api/v1/teams.updateRoom`       | Updates a room from a team, limited to permissions.       | [Link](core-endpoints/teams-endpoints/update-room-from-a-team.md)                                                                           |
| `/api/v1/teams.listRooms`        | Lists all rooms of the team.                              | [Link](core-endpoints/teams-endpoints/list-rooms-of-a-team.md)                                                                              |
| `/api/v1/teams.listRoomsOfUser`  | Lists only the team's rooms the user has joined.          | [Link](core-endpoints/teams-endpoints/list-rooms-of-user-of-a-team.md)                                                                      |
| `/api/v1/teams.members`          | Retrieves all team members.                               | [Link](core-endpoints/teams-endpoints/get-teams-members.md)                                                                                 |
| `/api/v1/teams.addMembers`       | Adds members to the team.                                 | [Link](core-endpoints/teams-endpoints/add-members.md)                                                                                       |
| `/api/v1/teams.updateMember`     | Updates a team member's roles, limited to permissions.    | [Link](core-endpoints/teams-endpoints/update-a-teams-member.md)                                                                             |
| `/api/v1/teams.removeMember`     | Removes a member from a team.                             | [Link](core-endpoints/teams-endpoints/remove-member-from-team.md)                                                                           |
| `/api/v1/teams.leave`            | Leaves a team.                                            | [Link](core-endpoints/teams-endpoints/leave-a-team.md)                                                                                      |
| `/api/v1/teams.info`             | Gets a team's information.                                | [Link](core-endpoints/teams-endpoints/get-teams-info.md)                                                                                    |
| `/api/v1/teams.delete`           | Removes a team.                                           | [Link](core-endpoints/teams-endpoints/delete-a-team.md)                                                                                     |
| `/api/v1/teams.autocomplete`     | Lists the teams whose names match a given pattern.        | [Link](core-endpoints/teams-endpoints/autocomplete-team.md)                                                                                 |
| `/api/v1/teams.update`           | Updates an existing team (name and type).                 | [Link](core-endpoints/teams-endpoints/update-a-team.md)                                                                                     |

## Users  <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                                           | Short Description                                              | Details Page                                                                                                                             |
| --------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/users.create`                        | Creates a new user                                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-user-endpoint)           |
| `/api/v1/users.delete`                        | Deletes an existing user                                       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/delete)                         |
| `/api/v1/users.deleteOwnAccount`              | Deletes your own user                                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/deleteownaccount)               |
| `/api/v1/users.getAvatar`                     | Gets the URL for a user’s avatar.                              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getavatar)                      |
| `/api/v1/users.setActiveStatus`               | Sets user's active status                                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-users-status-active)        |
| `/api/v1/users.deactivateIdle`                | Deactivates Idle users                                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/deactivate-idle-users)          |
| `/api/v1/users.getPresence`                   | Gets a user's presence                                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-presence)             |
| `/api/v1/users.info`                          | Retrieves information about a user                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-info)                 |
| `/api/v1/users.list`                          | Retrieves all of the users in the system and their information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-users-list)                 |
| `/api/v1/users.register`                      | Registers users                                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/register-users)                 |
| `/api/v1/users.resetAvatar`                   | Resets avatar                                                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/reset-avatar)                   |
| `/api/v1/users.setAvatar`                     | Sets avatar                                                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-avatar)                     |
| `/api/v1/users.getStatus`                     | Gets a user's status                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-status)                     |
| `/api/v1/users.setStatus`                     | Sets a user status                                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-status)                     |
| `/api/v1/users.update`                        | Updates user                                                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/update-user)                    |
| `/api/v1/users.updateOwnBasicInfo`            | Updates own basic information                                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/update-own-basic-information)   |
| `/api/v1/users.createToken`                   | Creates a user authentication token                            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-users-token)             |
| `/api/v1/users.getPreferences`                | Gets all preferences of the user.                              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/get-user-preferences)           |
| `/api/v1/users.setPreferences`                | Sets preferences of the user.                                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/set-preferences)                |
| `/api/v1/users.forgotPassword`                | Sends `an` email to reset your password.                       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/forgotpassword)                 |
| `/api/v1/users.getUsernameSuggestion`         | Suggestion of new username to user.                            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getusernamesuggestion)          |
| `/api/v1/users.generatePersonalAccessToken`   | Generates Personal Access Token                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/generatepersonalaccesstoken)    |
| `/api/v1/users.regeneratePersonalAccessToken` | Regenerates a user's personal access token                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/regeneratepersonalaccesstoken)  |
| `/api/v1/users.getPersonalAccessTokens`       | Gets the user’s personal access tokens                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/getpersonalaccesstokens)        |
| `/api/v1/users.removePersonalAccessToken`     | Removes a personal access token                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/removepersonalaccesstoken)      |
| `/api/v1/users.2fa.enableEmail`               | Enables 2fa email                                              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/enable-2fa-email)     |
| `/api/v1/users.2fa.disableEmail`              | Disables 2fa email                                             | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/disable-2fa-email)    |
| `/api/v1/users.2fa.sendEmailCode`             | Sends 2fa code                                                 | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/send-2fa-code)        |
| `/api/v1/users.presence`                      | Gets all connected users presence.                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/presence)                       |
| `/api/v1/users.requestDataDownload`           | Requests the user's data for download.                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/requestdatadownload)            |
| `/api/v1/users.logoutOtherClients`            | Logs out other clients                                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/logout-other-clients) |
| `/api/v1/users.autocomplete`                  | Lists the user whose names match a given pattern.              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/autocomplete-user)    |
| `/api/v1/users.removeOtherTokens`             | Removes other tokens                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/remove-other-tokens)            |
| `/api/v1/users.resetE2EKey`                   |                                                                | Document Under Development                                                                                                               |
| `/api/v1/users.resetTOTP`                     |                                                                | Document Under Development                                                                                                               |
| `/api/v1/users.listTeams`                     | Lists users teams                                              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/list-users-teams)     |
| `/api/v1/users.logout`                        | Logs user out.                                                 | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/logout-user-endpoint) |

## Video conference

| URL                                             | Short Description                                           | Details Page                                                                                                                              |
| ----------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/video-conference/jitsi.update-timeout` | Updates the timeout of Jitsi video conference in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout) |

## Webdav

| URL                            | Short Description                    | Details Page                                                                                                            |
| ------------------------------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/webdav.getMyAccounts` | Retrieves the user's webdav accounts | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts) |

## Federation (EE)

<table><thead><tr><th width="180">Url</th><th width="323">Short Description</th><th width="323.3333333333333">Details Page</th></tr></thead><tbody><tr><td><code>api/v1/federation/addServerByUser</code></td><td>Adds a server to search public rooms later</td><td><a href="federation-endpoints/add-server.md">Link</a></td></tr><tr><td><code>api/v1/federation/listServersByUser</code></td><td>Retrieves all the server names saved by the user</td><td><a href="federation-endpoints/list-servers.md">Link</a></td></tr><tr><td><code>api/v1/federation/removeServerByUser</code></td><td>Remove a server name</td><td><a href="federation-endpoints/remove-server.md">Link</a></td></tr><tr><td><code>api/v1/federation/searchPublicRooms</code></td><td>Returns all the public room given a server name</td><td><a href="federation-endpoints/search-public-rooms.md">Link</a></td></tr><tr><td><code>api/v1/joinExternalPublicRoom</code></td><td>Joins an External public Matrix room</td><td><a href="federation-endpoints/join-external-public-room.md">Link</a></td></tr></tbody></table>

## Livechat&#x20;

### Agent

| Url                               | Short Description                              | Details Page                                                                                                                                |
| --------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/agent.info/:rid/:token` | Retrieves the current omnichannel agent data   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/agent)      |
| `livechat/agent.next/:token`      | Retrieves the data of the next available agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/next-agent) |

### Configuration

| Url               | Short Description                                                         | Details Page                                                                                                                      |
| ----------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/config` | Retrieves LiveChat widget configuration info and additional visitor data. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-config) |

### Contacts

| Url                          | Short Description                                   | Details Page                                                                                                                                                    |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `omnichannel/contact`        | Registers a guest user as a new omnichannel contact | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/register-omnichannel-contact) |
| `omnichannel/contact`        | Retrieves a contact information                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-fetch-contact)    |
| `omnichannel/contact.search` | Searches a contact information                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-search-contact)   |

### Custom Field

| Url                           | Short Description                             | Details Page                                                                                                                                                            |
| ----------------------------- | --------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/custom.field`       | Sends a custom field                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-a-livechat-custom-field)            |
| `livechat/custom.fields`      | Sends an array of custom field                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-an-array-of-livechat-custom-fields) |
| `livechat/custom-fields`      | Retrieves a list of omnichannel custom fields | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/list-livechat-custom-fields)             |
| `livechat/custom-fields/:_id` | Retrieves info about a custom field           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/get-info-about-a-custom-field)           |

### Message

| Url                              | Short Description                      | Details Page                                                                                                                                                      |
| -------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/message`               | Sends a new omnichannel message        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/livechat-send-new-message)      |
| `livechat/message/:_id`          | Retrieves a specific message           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/retrieve-a-livechat-message)    |
| `livechat/message/:_id`          | Updates an omnichannel message         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/update-a-livechat-message)      |
| `livechat/message/:_id`          | Removes an omnichannel message         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/remove-a-livechat-message)      |
| `livechat/messages.history/:rid` | Retrieves omnichannel messages history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/load-livechat-messages-history) |
| `livechat/messages`              | Sends array of messages                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-message/send-an-array-of-messages)                            |

### Offline Message

| Url                        | Short Description                                   | Details Page                                                                                                                               |
| -------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/offline.message` | Sends an offline message when no agent is available | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-offline-message) |

### Page Visited

| Url                     | Short Description                                                    | Details Page                                                                                                                                      |
| ----------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/page.visited` | Retrieves the pages your omnichannel user navigated on your website. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-page-visited/send-visitor-navigation-history) |

### Room

| Url                      | Short Description                                                 | Details Page                                                                                                                                           |
| ------------------------ | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/room`          | GetRetrievesthe omnichannel room data or open a new conversation. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-info)     |
| `livechat/room.close`    | Closes an omnichannel conversation                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-close)    |
| `livechat/room.transfer` | Transfers an omnichannel conversation                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-transfer) |
| `livechat/room.forward`  | Chatbot agent forwards the chat to a human agent                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-forward)  |
| `livechat/room.visitor`  | Updates room visitor's information                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/change-room-visitor)    |

### Transcript

| Url                   | Short Description              | Details Page                                                                                                                          |
| --------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transcript` | Requests a Livechat transcript | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transcript) |

### Transfer

| Url                              | Short Description                           | Details Page                                                                                                                        |
| -------------------------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transfer.history/:rid` | Retrieves the conversation transfer history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transfer) |

### Visitor

| Url                            | Short Description                        | Details Page                                                                                                                                                 |
| ------------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/visitor`             | Registers a new visitor                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/register-a-new-livechat-visitor)    |
| `livechat/visitor/:token`      | Retrieves a visitor                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/retrieve-a-visitor-data)            |
| `livechat/visitor/:token`      | Deletes a visitor                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/delete-a-visitor)                   |
| `livechat/visitor/:token/room` | Retrieves open conversation of a visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/get-open-conversation-of-a-visitor) |
| `livechat/visitor.status`      | Sets visitor status                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/set-visitor-status)                 |

## Agent

<table><thead><tr><th width="272">Url</th><th width="276">Short Description</th><th width="323.3333333333333">Details Page</th></tr></thead><tbody><tr><td><code>api/v1/livechat/agents/:agentId/departments</code></td><td>Returns all the departments associated with an agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-departments">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/average-service-time</code></td><td>Retrieves average service time per agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-average-service-time">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/total-service-time</code></td><td>Retrieves total service time sorted by agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-total-service-time">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/available-for-service-history</code></td><td>Retrieves a list of agents and their available time for the provided time frame</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-available-for-service-history">Link</a></td></tr></tbody></table>

## Livechat Appearance

| Url                          | Short Description                                   | Details Page                                                                                              |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/appearance` | Retrieves LiveChat widget settings about appearance | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/appearance) |

## Business Hours

| Url                                   | Short Description                                           | Details Page                                                                                                                      |
| ------------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/business-hour`       | Retrieves all the information of a particular business hour | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/business-hours/business-hour-info)  |
| `api/v1/livechat/business-hours.list` | Retrieves a list of existing business hours                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/business-hours/business-hours-list) |

## Dashboards

| Url                                                                   | Short Description                                       | Details Page                                                                                                                            |
| --------------------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/analytics/dashboards/conversation-totalizers`        | Retrieves conversation totalizers for a department      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/conversation-totalizers)       |
| `api/v1/livechat/analytics/dashboards/agents-productivity-totalizers` | Retrieves agent productivity totalizer for a department | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/agent-productivity-totalizers) |
| `api/v1/livechat/analytics/dashboards/chats-totalizers`               | Retrieves chat totalizers for a department              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chat-totalizers)               |
| `api/v1/livechat/analytics/dashboards/productivity-totalizers`        | Retrieves productivity totalizers for a department      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/productivity-totalizers)       |
| `api/v1/livechat/analytics/dashboards/charts/chats`                   | Retrieves chats chat for a department                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-chart)                   |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-agent`         | Retrieves chats per agent for a department chart        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-per-agent-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/agents-status`           | Retrieves agent's statuses chart                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/agents-statuses-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-department`    | Retrieves chats per department chart                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-per-department-chart)    |
| `api/v1/livechat/analytics/dashboards/charts/timings`                 | Retrieves timing charts                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/timings-charts)                |

## Departments

| Url                                                                | Short Description                                             | Details Page                                                                                                                                  |
| ------------------------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/department`                                       | Retrieves a list of departments                               | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/get-a-list-of-departments)           |
| `api/v1/livechat/department`                                       | Registers a new department                                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/register-a-new-department)           |
| `api/v1/livechat/department/:_id`                                  | Retrieves a department's info                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/get-info-about-a-department)         |
| `api/v1/livechat/department/:_id`                                  | Updates a department                                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/update-a-department)                 |
| `api/v1/livechat/department/:_id`                                  | Removes a department                                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/remove-a-department)                 |
| `api/v1/livechat/department.autocomplete`                          | Autocompletes department name                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/department-autocomplete)             |
| `api/v1/livechat/department/:departmentId/agents`                  | Retrieves agents of a specific department                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/retrieve-agents-of-a-department)     |
| `api/v1/livechat/department/:departmentId/agents`                  | Updates agents of a department                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/update-agents-of-a-department)       |
| `api/v1/livechat/department.listByIds`                             | Retrieves a list of departments by an array of department ids | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/listing-departments-by-ids)          |
| `api/v1/livechat/departments.available-by-unit/:unitId`            | Retrieves departments available by unit Id                    | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/departments-available-by-unit-id)                           |
| `api/v1/livechat/analytics/departments/amount-of-chats`            | Retrieves the number of incoming chats                        | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/amount-of-chat)                                             |
| `api/v1/livechat/analytics/departments/average-service-time`       | Retrieves average service time                                | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-service-time-by-department)                         |
| `api/v1/livechat/analytics/departments/average-chat-duration-time` | Retrieves average chats duration                              | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-chat-duration-time-by-department)                   |
| `api/v1/livechat/analytics/departments/total-service-time`         | Retrieves total service time                                  | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-service-time-by-department)                           |
| `api/v1/livechat/analytics/departments/average-waiting-time`       | Retrieves avg waiting time                                    | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-waiting-time-by-department)                         |
| `api/v1/livechat/analytics/departments/total-transferred-chats`    | Retrieves total transferred chats                             | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-transferred-chat-by-department)                       |
| `api/v1/livechat/analytics/departments/total-abandoned-chats`      | Retrieves abandoned chats                                     | [Info](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/total-abandoned-chats-by-department) |
| `api/v1/livechat/analytics/departments/percentage-abandoned-chats` | Retrieves percentage of abandoned chats                       | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/percentage-of-abandoned-chats-by-department)                |

## Inquiries

| Url                                  | Short Description                        | Details Page                                                                                                                |
| ------------------------------------ | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/inquiries.list`     | Lists all of the open livechat inquiries | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list)     |
| `api/v1/livechat/inquiries.take`     | Takes an open inquiry                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/take-inquiry)       |
| `api/v1/livechat/inquiries.queued`   | Lists queued inquiries                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-queued)   |
| `api/v1/livechat/inquiries.getOne`   | Gets one inquiry by room id              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiry-get-one)    |
| `api/v1/livechat/inquiry.prioritize` | Sets the priority of an inquiry          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiry-prioritize) |

## Integrations

| Url                                     | Short Description                        | Details Page                                                                                                |
| --------------------------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/integrations.settings` | Retrieves a list of integration settings | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/integrations) |

## Queue

| Url                     | Short Description          | Details Page                                                                                                  |
| ----------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/queue` | Retrieves the queued chats | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/livechat-queue) |

## Rooms

| Url                           | Short Description                            | Details Page                                                                                                             |
| ----------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/rooms`       | Retrieves a list of livechat rooms           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/rooms/livechat-rooms-list) |
| `api/v1/livechat/room.onHold` | Puts an active livechat conversation on hold | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/rooms/room-onhold)         |

## SMS

| Url                                     | Short Description | Details Page                                                                                                       |
| --------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/sms-incoming/:service` | Receives SMS      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/sms-incoming-twilio) |

## Triggers

| Url                             | Short Description                  | Details Page                                                                                                                      |
| ------------------------------- | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/triggers`      | Lists all Livechat triggers        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/triggers/get-the-livechat-triggers) |
| `api/v1/livechat/triggers/:_id` | Retrieves a Livechat Trigger by id | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/triggers/get-a-livechat-trigger)    |

## Upload

| Url                           | Short Description | Details Page |
| ----------------------------- | ----------------- | ------------ |
| `api/v1/livechat/upload/:rid` | post              |              |

## Live chat Users

| Url                                | Short Description                   | Details Page                                                                                                                         |
| ---------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/users/:type`      | Gets a list of agents or managers   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/users)     |
| `api/v1/livechat/users/:type`      | Registers a new agent or manager    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/register-new-agent-or-manager)   |
| `api/v1/livechat/users/:type/:_id` | Gets info about an agent or manager | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/get-info-of-an-agent-or-manager) |
| `api/v1/livechat/users/:type/:_id` | Removes an agent or manager         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/remove-an-agent-or-manager)      |

## Visitors

| Url                                                                    | Short Description                           | Details Page                                                                                                                                  |
| ---------------------------------------------------------------------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/visitors.info`                                        | Retrieves visitor info by ID                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitor-info-by-id)                    |
| `api/v1/livechat/visitors.pagesVisited/:roomId`                        | Retrieves pages visited by livechat visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/get-pages-visited-by-livechat-visitor) |
| `api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId` | Retrieves livechat visitor's chat history   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/get-livechat-visitors-chat-history)    |
| `api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId` | Searches a visitor's chat                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/search-a-visitors-chat)                |
| `api/v1/livechat/visitors.autocomplete`                                | Autocompletes visitor's name                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitor-autocomplete)                  |
| `api/v1/livechat/visitors.search`                                      | Searches the visitor by the term            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitors-search)                       |

## Monitors

| Url                               | Short Description              | Details Page                                                                                                             |
| --------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/monitors.list`   | Retrieves a list of monitors   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/monitors/list-of-monitors) |
| `api/v1/livechat/monitors.getOne` | Gives the details of a monitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/monitors/get-one-monitor)  |

## Priorities

| Url                                      | Short Description               | Details Page                                        |
| ---------------------------------------- | ------------------------------- | --------------------------------------------------- |
| `api/v1/livechat/priorities`             | Gives a list of priorities      | [Link](priorities/priorities-old/get-priorities.md) |
| `api/v1/livechat/priorities/:priorityId` | Gives the details of a priority | [Link](priorities/priorities-old/get-a-priority.md) |

## Livechat Tags

| Url                           | Short Description          | Details Page                       |
| ----------------------------- | -------------------------- | ---------------------------------- |
| `api/v1/livechat/tags`        | Retrieves a list of tags   | [Link](livechat-tags/get-tags.md)  |
| `api/v1/livechat/tags.getOne` | Retrieves details of a tag | [Link](livechat-tags/get-a-tag.md) |

## Units

| Url                                     | Short Description             | Details Page                                                                                                                   |
| --------------------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/units`                 | Create unit                   | [Link](units/create-unit.md)                                                                                                   |
| `api/v1/livechat/units.list`            | Gives a list of units         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit)          |
| `api/v1/livechat/units.getOne`          | Retrieves details of a unit   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/get-one-unit)          |
| `api/v1/livechat/unitMonitors.list`     | Gives a list of unit monitors | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit-monitors) |
| `api/v1/livechat/unitMonitors.list/:id` | Update Unit by Id             | [Link](units/update-unit.md)                                                                                                   |
| `api/v1/livechat/unitMonitors.list/:id` | Delete unit using ID          | [Link](units/delete-unit.md)                                                                                                   |

## SLA Policies

| URL                          | Description                                         | Details Page                                                                                                            |
| ---------------------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/sla`        | Get a list of SLA policies and create an SLA policy | [Fetch](sla-policies/get-sla-policies.md), [Create](core-endpoints/teams-endpoints/create-a-new-team.md)                |
| `api/v1/livechat/sla/:slaId` | Used to fetch, update and delete an SLA policy      | [Get one](sla-policies/get-an-sla.md), [Update](sla-policies/update-an-sla.md), [Delete](sla-policies/delete-an-sla.md) |

## Voice Channel

| URL                                                                                           | Description                                     | Details Page                                                                           |
| --------------------------------------------------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------- |
| `/v1/connector.extension.getRegistrationInfoByUserId`                                         | Get registration information by ID              | [Link](./#voip-registration-information)                                               |
| `/api/v1/voip/queues.getSummary`                                                              | Get VoIP query summary data                     | [Link](./#voip-query-summary)                                                          |
| `/api/v1/voip/queues.getSummary`                                                              | Get VoIP query summary data                     | [Link](./#voip-query-summary)                                                          |
| `/api/v1/voip/queues.getSummary`                                                              | Get VoIP queue membership data                  | [Link](voice-channel-queue-membership/get-call-center-queue-membership-information.md) |
| `/v1/voip/queues.getMembershipSubscription`                                                   | Get VoIP queue membership subscription data     | [Link](./#voip-queue-membership)                                                       |
| `/v1/voip/queues.getMembershipSubscription`                                                   | Get VoIP queue membership subscription data     | [Link](./#voip-queue-membership)                                                       |
| `v1/voip/queues.getMembershipSubscription`                                                    | Get the VoIP queue membership subscription data | [Link](./#voip-queue-membership)                                                       |
| `api/v1/livechat/visitor`                                                                     | Create a VoIP visitor                           | [Link](./#create-visitor)                                                              |
| `/api/v1/voip/events`                                                                         | Send VoIP events                                | [Link](./#send-voip-events)                                                            |
| `/api/v1/omnichannel/extension`                                                               | Retrieve VoIP extension information             | [Link](./#fetch-voip-extensions)                                                       |
| `/api/v1/omnichannel/extensions?count=10&offset=10`                                           | Retrieve VoIP extensions                        | [Link](./#fetch-voip-extensions)                                                       |
| `/v1/omnichannel/agent/extension`                                                             | Create, update and delete VoIP extension        | [Link](./#agent-extensions)                                                            |
| `/api/v1/voip/managementServer/checkConnection?host&port&username&password`                   | Check management server connection status       | [Link](./#check-management-server-connection)                                          |
| `/api/v1/voip/callServer/checkConnection?websocketUrl=wss://omni-asterisk.dev.rocket.chat/ws` | Check call server connection status             | [Link](./#check-call-server-connection)                                                |
| `/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba&agentId=6vHSSqdBHdm2R4gfi`          | Create VoIP room                                | [Link](./#create-voip-room)                                                            |
| `/api/v1/voip/events`                                                                         | Retrieve VoIP room information by ID            | [Link](./#fetch-voip-room-by-id)                                                       |
| `/api/v1/voip/room.clos`                                                                      | Close the VoIP conversation                     | [Link](./#close-voip-room)                                                             |

## Licenses

| Url                             | Short Description                            | Details Page                                   |
| ------------------------------- | -------------------------------------------- | ---------------------------------------------- |
| `/api/v1/licenses.get`          | Gets all registered licenses.                | [Link](licenses/get-licenses.md)               |
| `/api/v1/licenses.isEnterprise` | Confirm if workspace has enterprise license. | [Link](licenses/confirm-enterprise-license.md) |
| `licenses.maxActiveUsers`       | Get maximum active users.                    | [Link](licenses/get-maximum-active-user.md)    |

## WhatsApp

| Description                                       | Details Page                                                                      |
| ------------------------------------------------- | --------------------------------------------------------------------------------- |
| WhatsApp Business API integration for Rocket.Chat | [Link](apps-endpoints/whatsapp-endpoints/whatsapp-omnichannel-integration-api.md) |
| Send a template message.                          | [Link](apps-endpoints/whatsapp-endpoints/template-message.md)                     |
