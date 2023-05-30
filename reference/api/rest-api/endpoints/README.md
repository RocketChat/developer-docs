# Endpoints

## Assets Endpoints

| URL                         | Short Description            | Details Page                                                                                      |
| --------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------- |
| `/api/v1/assets.setAsset`   | Sets an asset image by name. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset)   |
| `/api/v1/assets.unsetAsset` | Unsets an asset by name.     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset) |

## Auto Translate Endpoints

| URL                                           | Short Description                               | Details Page                                                                                                        |
| --------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/autotranslate.getSupportedLanguages` | Gets the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings`          | Saves some settings about auto-translate.       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings)          |
| `/api/v1/autotranslate.translateMessage`      | Translates the message.                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage)      |

## Banners Endpoints

| URL                       | Short Description                                      | Details Page                                                                                                                 |
| ------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/banners/:id`     | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banner-by-id) |
| `/api/v1/banners`         | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banners)      |
| `/api/v1/banners.dismiss` | Dismisses a banner                                     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/dismiss-a-banner) |

## Channels Endpoints

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

## Chat Endpoints

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

## Cloud Endpoints

| URL                            | Short Description              | Details Page                                                                                                                              |
| ------------------------------ | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/cloud.manualRegister` | Manually registers a workspace | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/cloud-endpoints/cloud-manual-register) |

## Commands Endpoints

| URL                        | Short Description                                                         | Details Page                                                                                                                     |
| -------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/commands.get`     | Retrieves the specification of the slash command.                         | [Link](core-endpoints/commands-endpoints/get-slash-commands.md)                                                                  |
| `/api/v1/commands.list`    | Lists all available slash commands.                                       | [Link](core-endpoints/commands-endpoints/list.md)                                                                                |
| `/api/v1/commands.run`     | Executes a slash command in the specified room.                           | [Link](core-endpoints/commands-endpoints/execute-a-slash-command.md)                                                             |
| `/api/v1/commands.preview` | Retrieves the preview data for the command and executes the preview item. | [Link](core-endpoints/commands-endpoints/preview.md)                                                                             |
| `/api/v1/commands.preview` | Executes command's preview item                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/commands/execute-commands-preview-item) |

## Custom Sounds Endpoints

| URL                          | Short Description                  | Details Page                                                                                                                                                     |
| ---------------------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | [Link](https://app.gitbook.com/@rocket-chat/s/rocket-chat-developer/\~/drafts/-MgSmy428hAP1znS6g3V/api/rest-api/endpoints/team-collaboration/custom-sounds/list) |

## Custom User Status Endpoints

| URL                                 | Short Description                         | Details Page                                                                                                                                                    |
| ----------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-user-status.list`   | Lists all available custom user's status. | [Link](core-endpoints/custom-user-status-endpoints/list.md)                                                                                                     |
| `/api/v1/custom-user-status.create` | Creates custom user status                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/create-custom-user-status)      |
| `/api/v1/custom-user-status.delete` | Deletes a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/delete-custom-user-status)      |
| `/api/v1/custom-user-status.update` | Updates a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/update-custom-user-status-type) |

## DNS Endpoints

| URL                       | Short Description                                      | Details Page                                                                                                                      |
| ------------------------- | ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/dns.resolve.srv` | get                                                    | Document Under Development                                                                                                        |
| `/api/v1/dns.resolve.txt` | Resolves DNS text records (TXT records) for a hostname | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/dns-endpoints/dns-resolve-txt) |

## E2E Endpoints

| URL                                       | Short Description                                               | Details Page                                                                                                                                        |
| ----------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/e2e.fetchMyKeys`                 | Retrieves E2E keys of logged in user                            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/fetch-your-e2e-keys)               |
| `/api/v1/e2e.getUsersOfRoomWithoutKey`    | Retrieves Users Of Room Without E2E Key                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/get-users-of-room-without-e2e-key) |
| `/api/v1/e2e.setRoomKeyID`                | Sets the end-to-end encryption key ID for a room                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-room-e2e-key)                  |
| `/api/v1/e2e.setUserPublicAndPrivateKeys` | Sets the end-to-end encryption keys for the authenticated user. | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-users-key)                     |
| `/api/v1/e2e.updateGroupKey`              | Updates the end-to-end encryption key for a user in a room.     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/update-user-e2e-key-in-room)       |

## Email Inbox Endpoints

| URL                                  | Short Description                    | Details Page                                                                                                                                             |
| ------------------------------------ | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/email-inbox.list`           | Retrieves mail Inbox list            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-list)               |
| `/api/v1/email-inbox`                | Sets the email inbox for your server | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/set-email-inbox)                |
| `/api/v1/email-inbox/:_id`           | Retrieves email Inbox by id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-by-id)              |
| `/api/v1/email-inbox/:_id`           | Delete email inbox using id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/delete-email-inbox-by-id)       |
| `/api/v1/email-inbox.search`         | Searches email inbox by address      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/search-email-inbox-by-email)    |
| `/api/v1/email-inbox.send-test/:_id` | Sends test email to email inbox      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/send-test-email-to-email-inbox) |

## Custom Emojis Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                           | Short Description                          | Details Page                                                                                                                                      |
| ----------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/emoji-custom.all`    | Retrieves all custom emojis                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-emoji-endpoints/list-all-custom-emojis) |
| `/api/v1/emoji-custom.list`   | Retrieves an updated list of custom emojis | [Link](core-endpoints/custom-emoji-endpoints/list-custom-emojis.md)                                                                               |
| `/api/v1/emoji-custom.create` | Creates new custom emoji.                  | [Link](core-endpoints/custom-emoji-endpoints/create-new-custom-emoji.md)                                                                          |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji.           | [Link](core-endpoints/custom-emoji-endpoints/delete-custom-emoji.md)                                                                              |
| `/api/v1/emoji-custom.update` | Updates an existent custom emoji.          | [Link](core-endpoints/custom-emoji-endpoints/update-a-custom-emoji.md)                                                                            |

## Groups Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## IM Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

From version 0.50.0 and on you can call the methods using `dm` instead of `im`.

## Imports Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## **Instances** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                     | Short Description   | Details Page                                                                                                                          |
| ----------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/instances.get` | Retrieves instances | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/instances-endpoints/get-instances) |

## **Integrations** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                            | Short Description                               | Details Page                                            |
| ------------------------------ | ----------------------------------------------- | ------------------------------------------------------- |
| `/api/v1/integrations.create`  | Creates an integration.                         | [Link](core-endpoints/integration-endpoints/create.md)  |
| `/api/v1/integrations.get`     | Gets an integration.                            | [Link](core-endpoints/integration-endpoints/get.md)     |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](core-endpoints/integration-endpoints/history.md) |
| `/api/v1/integrations.list`    | Lists all of the integrations.                  | [Link](core-endpoints/integration-endpoints/list.md)    |
| `/api/v1/integrations.remove`  | Removes an integration.                         | [Link](core-endpoints/integration-endpoints/remove.md)  |
| `/api/v1/integrations.update`  | Updates an integration.                         | [Link](core-endpoints/integration-endpoints/update.md)  |

## **Invites** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                           | Short Description                                                         | Details Page                                                                                                                             |
| ----------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/findOrCreateInvite`  | Created a new Invite or returns an existing one with the same parameters. | [Link](core-endpoints/invite-endpoints/findorcreateinvite.md)                                                                            |
| `/api/v1/listInvites`         | Lists all of the invite tokens.                                           | [Link](core-endpoints/invite-endpoints/listinvites.md)                                                                                   |
| `/api/v1/removeInvite/:_id`   | Deletes an invite from the server.                                        | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/invite-endpoints/delete-invite-by-id) |
| `/api/v1/useInviteToken`      | Reports to the server that an invite token was used.                      | [Link](core-endpoints/invite-endpoints/report-use-invite-token.md)                                                                       |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid.                                       | [Link](core-endpoints/invite-endpoints/validateinvitetoken.md)                                                                           |

## **Misc** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

Just some generic information, such as information about the server and authenticated user.

| Url                    | Short Description                                                                | Details Page                                                                                                                                 |
| ---------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/directory`    | Searches by all users and channels available on server.                          | [Link](core-endpoints/miscellaneous-endpoints/directory.md)                                                                                  |
| `/api/v1/shield.svg`   | Gets the shield SVG (badge) to add in your website.                              | [Link](core-endpoints/miscellaneous-endpoints/shield-svg.md)                                                                                 |
| `/api/v1/spotlight`    | Searches for users or rooms that are visible to the user.                        | [Link](core-endpoints/miscellaneous-endpoints/spotlight.md)                                                                                  |
| `/api/v1/me`           | Gets user data of the authenticated user                                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/miscellaneous-endpoints/get-user-data)    |
| `/api/v1/stdout.queue` | Retrieves last 1000 lines of server logsRetrieves last 1000 lines of server logs | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/miscellaneous-endpoints/get-stdout-queue) |

## **Oauth apps** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                       | Short Description                          | Details Page                                       |
| ------------------------- | ------------------------------------------ | -------------------------------------------------- |
| `/api/v1/oauth-apps.get`  | Retrieves an OAuth App by id or client id. | [Link](core-endpoints/oauthapps-endpoints/get.md)  |
| `/api/v1/oauth-apps.list` | Retrieves a list of OAuth Apps.            | [Link](core-endpoints/oauthapps-endpoints/list.md) |

## **Permissions** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                           | Short Description                | Details Page                                                         |
| ----------------------------- | -------------------------------- | -------------------------------------------------------------------- |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](core-endpoints/permissions-endpoints/list-all-permissions.md) |
| `/api/v1/permissions.update`  | Edits permissions on the server. | [Link](core-endpoints/permissions-endpoints/update-permissions.md)   |

## **Push** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                  | Short Description                   | Details Page                                                                                                                                       |
| -------------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/push.token` | Saves push token.                   | [Link](core-endpoints/push-token-endpoints/push-token.md)                                                                                          |
| `/api/v1/push.token` | Removes push token.                 | [Link](core-endpoints/push-token-endpoints/deletepushtoken.md)                                                                                     |
| `/api/v1/push.get`   | Get push notification for a message | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/push-token-endpoints/Get%20push%20notification) |

## **Roles** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## **Rooms** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## **Settings** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

You can get and update the settings via the REST API, only if you have permission to.

| Url                              | Method | Short Description                             | Details Page                                                            |
| -------------------------------- | ------ | --------------------------------------------- | ----------------------------------------------------------------------- |
| `/api/v1/settings`               | `GET`  | Lists all private settings.                   | [Link](core-endpoints/settings-endpoints/get-private-settings.md)       |
| `/api/v1/settings.public`        | `GET`  | Lists all public settings.                    | [Link](core-endpoints/settings-endpoints/get-public-settings.md)        |
| `/api/v1/settings.oauth`         | `GET`  | Returns list of all available oauth services. | [Link](core-endpoints/settings-endpoints/get-all-oauth.md)              |
| `/api/v1/service.configurations` | `GET`  | Lists all service configurations.             | [Link](core-endpoints/settings-endpoints/get-service-configurations.md) |
| `/api/v1/settings/:_id`          | `GET`  | Retrieves a setting.                          | [Link](core-endpoints/settings-endpoints/get-setting-by-id.md)          |
| `/api/v1/settings/:_id`          | `POST` | Updates a setting.                            | [Link](core-endpoints/settings-endpoints/update-setting.md)             |

## **Stats** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                       | Short Description         | Details Page                                                                                                                            |
| ------------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/statistics`      | Retrieves statistics      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics)      |
| `/api/v1/statistics.list` | Retrieves statistics list | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics-list) |

## **Subscriptions** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| Url                            | Short Description                      | Details Page                                                              |
| ------------------------------ | -------------------------------------- | ------------------------------------------------------------------------- |
| `/api/v1/subscriptions.get`    | Retrieves all subscriptions.           | [Link](core-endpoints/subscriptions-endpoints/get-all-subscriptions.md)   |
| `/api/v1/subscriptions.getOne` | Retrieves the subscription by room Id. | [Link](core-endpoints/subscriptions-endpoints/get-subscription-room.md)   |
| `/api/v1/subscriptions.read`   | Marks a room as read.                  | [Link](core-endpoints/subscriptions-endpoints/mark-channel-as-read.md)    |
| `/api/v1/subscriptions.unread` | Marks messages as unread.              | [Link](core-endpoints/subscriptions-endpoints/mark-messages-as-unread.md) |

## **Teams** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## **Users** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

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

## **Video Conference** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                                             | Short Description                                           | Details Page                                                                                                                              |
| ----------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/video-conference/jitsi.update-timeout` | Updates the timeout of Jitsi video conference in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout) |

## **Webdav** Endpoints <a href="#email-inbox-endpoints" id="email-inbox-endpoints"></a>

| URL                            | Short Description                    | Details Page                                                                                                            |
| ------------------------------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/webdav.getMyAccounts` | Retrieves the user's webdav accounts | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts) |

## Federation (EE)

<table><thead><tr><th width="180">Url</th><th width="323">Short Description</th><th width="323.3333333333333">Details Page</th></tr></thead><tbody><tr><td><code>api/v1/federation/addServerByUser</code></td><td>Adds a server to search public rooms later</td><td><a href="add-federated-server.md">Link</a></td></tr><tr><td><code>api/v1/federation/listServersByUser</code></td><td>Retrieves all the server names saved by the user</td><td><a href="list-servers.md">Link</a></td></tr><tr><td><code>api/v1/federation/removeServerByUser</code></td><td>Remove a server name</td><td><a href="remove-federated-server.md">Link</a></td></tr><tr><td><code>api/v1/federation/searchPublicRooms</code></td><td>Returns all the public room given a server name</td><td><a href="search-public-rooms.md">Link</a></td></tr><tr><td><code>api/v1/joinExternalPublicRoom</code></td><td>Joins an External public Matrix room</td><td><a href="join-external-public-room.md">Link</a></td></tr></tbody></table>

