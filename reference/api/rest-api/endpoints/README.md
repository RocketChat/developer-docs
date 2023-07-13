# Endpoints

## Authentication

| Url              | Short Description                                  | Details Page                                 |
| ---------------- | -------------------------------------------------- | -------------------------------------------- |
| `/api/v1/login`  | Authenticate with username and password.           | [Link](authentication-endpoints/login.md)    |
| `/api/v1/login`  | Authenticate with facebook.                        | [Link](authentication-endpoints/facebook.md) |
| `/api/v1/login`  | Authenticate with google.                          | [Link](authentication-endpoints/google.md)   |
| `/api/v1/login`  | Authenticate with twitter.                         | [Link](authentication-endpoints/twitter.md)  |
| `/api/v1/logout` | Invalidate your REST API authentication token.     | [Link](authentication-endpoints/logout.md)   |
| `/api/v1/me`     | Displays information about the authenticated user. | [Link](authentication-endpoints/me.md)       |

## User Management

### Avatar

| URL                | Short Description    | Details Page     |
| ------------------ | -------------------- | ---------------- |
| `/avatar/{subject}`| Fetch room avatar    | [Link](user-management/avatars.md) |

### Users

| URL                                      | Short Description                   | Details Page                                                    |
| ---------------------------------------- | ---------------------------------- | --------------------------------------------------------------- |
| `/api/v1/users.create`                   | Creates a new user                 | [Link](user-management/users-endpoints/create-user.md)          |
| `/api/v1/users.delete`                   | Deletes an existing user           | [Link](user-management/users-endpoints/delete.md)                |
| `/api/v1/users.deleteOwnAccount`         | Deletes your own user              | [Link](user-management/users-endpoints/deleteownaccount.md)      |
| `/api/v1/users.getAvatar`                | Gets the URL for a user’s avatar   | [Link](user-management/users-endpoints/getavatar.md)             |
| `/api/v1/users.setActiveStatus`          | Sets user's active status          | [Link](user-management/users-endpoints/set-users-status-active.md) |
| `/api/v1/users.deactivateIdle`           | Deactivates Idle users             | [Link](user-management/users-endpoints/deactivate-idle-users.md) |
| `/api/v1/users.getPresence`              | Gets a user's presence             | [Link](user-management/users-endpoints/get-users-presence.md)    |
| `/api/v1/users.info`                     | Retrieves information about a user | [Link](user-management/users-endpoints/get-users-info.md)        |
| `/api/v1/users.list`                     | Retrieves all of the users         | [Link](user-management/users-endpoints/get-users-list.md)        |
| `/api/v1/users.register`                 | Registers users                    | [Link](user-management/users-endpoints/register-users.md)        |
| `/api/v1/users.resetAvatar`              | Resets avatar                      | [Link](user-management/users-endpoints/reset-avatar.md)          |
| `/api/v1/users.setAvatar`                | Sets avatar                        | [Link](user-management/users-endpoints/set-avatar.md)            |
| `/api/v1/users.getStatus`                | Gets a user's status               | [Link](user-management/users-endpoints/get-status.md)            |
| `/api/v1/users.setStatus`                | Sets a user status                 | [Link](user-management/users-endpoints/set-status.md)            |
| `/api/v1/users.update`                   | Updates user                       | [Link](user-management/users-endpoints/update-user.md)           |
| `/api/v1/users.updateOwnBasicInfo`       | Updates own basic information      | [Link](user-management/users-endpoints/update-own-basic-information.md) |
| `/api/v1/users.createToken`              | Creates a user authentication token| [Link](user-management/users-endpoints/create-users-token.md)    |
| `/api/v1/users.getPreferences`           | Gets all preferences of the user   | [Link](user-management/users-endpoints/get-user-preferences.md)  |
| `/api/v1/users.setPreferences`           | Sets preferences of the user       | [Link](user-management/users-endpoints/set-preferences.md)       |
| `/api/v1/users.forgotPassword`           | Sends an email to reset your password | [Link](user-management/users-endpoints/forgotpassword.md)       |
| `/api/v1/users.getUsernameSuggestion`    | Suggestion of new username to user | [Link](user-management/users-endpoints/getusernamesuggestion.md) |
| `/api/v1/users.generatePersonalAccessToken` | Generates Personal Access Token | [Link](user-management/users-endpoints/generatepersonalaccesstoken.md) |
| `/api/v1/users.regeneratePersonalAccessToken` | Regenerates a user's personal access token | [Link](user-management/users-endpoints/regeneratepersonalaccesstoken.md) |
| `/api/v1/users.getPersonalAccessTokens` | Gets the user’s personal access tokens | [Link](user-management/users-endpoints/getpersonalaccesstokens.md) |
| `/api/v1/users.removePersonalAccessToken` | Removes a personal access token   | [Link](user-management/users-endpoints/removepersonalaccesstoken.md) |
| `/api/v1/users.2fa.enableEmail`          | Enables 2fa email                  | [Link](user-management/users-endpoints/enable-2fa-email.md)       |
| `/api/v1/users.2fa.disableEmail`         | Disables 2fa email                 | [Link](user-management/users-endpoints/disable-2fa-email.md)      |
| `/api/v1/users.2fa.sendEmailCode`        | Sends 2fa code                     | [Link](user-management/users-endpoints/send-2fa-code.md)          |
| `/api/v1/users.presence`                 | Gets all connected users presence | [Link](user-management/users-endpoints/presence.md)               |
| `/api/v1/users.requestDataDownload`      | Requests the user's data for download | [Link](user-management/users-endpoints/requestdatadownload.md)  |
| `/api/v1/users.logoutOtherClients`       | Logs out other clients             | [Link](user-management/users-endpoints/logout-other-clients.md)    |
| `/api/v1/users.autocomplete`             | Lists the user whose names match a given pattern | [Link](user-management/users-endpoints/autocomplete-user.md)  |
| `/api/v1/users.removeOtherTokens`        | Removes other tokens               | [Link](user-management/users-endpoints/remove-other-tokens.md)     |
| `/api/v1/users.resetE2EKey`              | Reset the E2E key for a user       | [Link](user-management/users-endpoints/reset-users-e2e-key.md)     |
| `/api/v1/users.resetTOTP`                | Reset the Two-factor authentication via TOTP | [Link](user-management/users-endpoints/reset-users-totp.md)    |
| `/api/v1/users.listTeams`                | Lists users teams                  | [Link](user-management/users-endpoints/list-users-teams.md)       |
| `/api/v1/users.logout`                   | Logs user out                      | [Link](user-management/users-endpoints/logout-user-endpoint.md)   |

### LDAP

| Url                    | Short Description | Details Page                            |
| ---------------------- | ----------------- | --------------------------------------- |
| `/api/v1/ldap.syncNow` | LDAP SyncNow      | [Link](user-management/ldap-endpoints/ldap-syncnow.md) |

### Permissions

| Url                           | Short Description                | Details Page                                                         |
| ----------------------------- | -------------------------------- | -------------------------------------------------------------------- |
| `/api/v1/permissions.listAll` | Lists permissions on the server. | [Link](user-management/permissions-endpoints/list-all-permissions.md) |
| `/api/v1/permissions.update`  | Edits permissions on the server. | [Link](user-management/permissions-endpoints/update-permissions.md)   |

### Roles

| Url                            | Short Description                                  | Details Page                                                   |
| ------------------------------ | -------------------------------------------------- | -------------------------------------------------------------- |
| `/api/v1/roles.list`           | Lists all roles on the server                      | [Link](user-management/roles-endpoints/list.md)                |
| `/api/v1/roles.sync`           | Lists all roles on the server updated after a date | [Link](user-management/roles-endpoints/sync.md)                |
| `/api/v1/roles.create`         | Creates a new role                                 | [Link](user-management/roles-endpoints/create.md)              |
| `/api/v1/roles.addUserToRole`  | Edits permissions on the server                    | [Link](user-management/roles-endpoints/addusertorole.md)       |
| `/api/v1/roles.getUsersInRole` | Retrieves users that belong to a role               | [Link](user-management/roles-endpoints/getusersinrole.md)      |
| `/api/v1/roles.update`         | Updates an existing role in the system             | [Link](user-management/roles-endpoints/update.md)              |
| `/api/v1/roles.delete`         | Deletes a role                                    | [Link](user-management/roles-endpoints/delete.md)              |
| `/api/v1/roles.removeUserFromRole` | Unassigns a role from a user                    | [Link](user-management/roles-endpoints/role-remove.md)         |

## Rooms

### Group

| Url                                | Short Description                                    | Details Page                                                   |
| ---------------------------------- | ---------------------------------------------------- | -------------------------------------------------------------- |
| `/api/v1/groups.addAll`            | Adds all users to a private group                    | [Link](rooms/groups-endpoints/addall.md)                       |
| `/api/v1/groups.addLeader`         | Gives Leader role to a user in the current group     | [Link](rooms/groups-endpoints/addleader.md)                    |
| `/api/v1/groups.addModerator`      | Gives moderator role to a user in a group            | [Link](rooms/groups-endpoints/addmoderator.md)                 |
| `/api/v1/groups.addOwner`          | Gives owner role to a user in a group                | [Link](rooms/groups-endpoints/addowner.md)                     |
| `/api/v1/groups.archive`           | Archives a private group                             | [Link](rooms/groups-endpoints/archive.md)                      |
| `/api/v1/groups.close`             | Removes a private group from the list of groups      | [Link](rooms/groups-endpoints/close.md)                        |
| `/api/v1/groups.counters`          | Retrieves group counters                             | [Link](rooms/groups-endpoints/counters.md)                     |
| `/api/v1/groups.create`            | Creates a new private group                          | [Link](rooms/groups-endpoints/create.md)                       |
| `/api/v1/groups.delete`            | Removes a private group                              | [Link](rooms/groups-endpoints/delete.md)                       |
| `/api/v1/groups.files`             | Retrieves files from a private group                 | [Link](rooms/groups-endpoints/files.md)                        |
| `/api/v1/groups.getIntegrations`   | Retrieves integrations assigned to the group         | [Link](rooms/groups-endpoints/getintegrations.md)              |
| `/api/v1/groups.history`           | Retrieves messages from a private group              | [Link](rooms/groups-endpoints/history.md)                      |
| `/api/v1/groups.info`              | Retrieves information about a private group          | [Link](rooms/groups-endpoints/info.md)                         |
| `/api/v1/groups.invite`            | Adds a user to the private group                     | [Link](rooms/groups-endpoints/invite.md)                       |
| `/api/v1/groups.kick`              | Removes a user from a private group                  | [Link](rooms/groups-endpoints/kick.md)                         |
| `/api/v1/groups.leave`             | Removes the caller from the private group            | [Link](rooms/groups-endpoints/leave.md)                        |
| `/api/v1/groups.list`              | Lists private groups the caller is part of           | [Link](rooms/groups-endpoints/list.md)                         |
| `/api/v1/groups.listAll`           | Lists all private groups                              | [Link](rooms/groups-endpoints/listall.md)                      |
| `/api/v1/groups.moderators`        | Lists moderators of a group                          | [Link](rooms/groups-endpoints/moderators.md)                   |
| `/api/v1/groups.members`           | Retrieves users of a private group                   | [Link](rooms/groups-endpoints/members.md)                      |
| `/api/v1/groups.messages`          | Retrieves all group messages                         | [Link](rooms/groups-endpoints/messages.md)                     |
| `/api/v1/groups.online`            | Lists online users of a group                        | [Link](rooms/groups-endpoints/online.md)                       |
| `/api/v1/groups.open`              | Adds the private group back to the list of groups     | [Link](rooms/groups-endpoints/open.md)                         |
| `/api/v1/groups.removeLeader`      | Removes Leader role from a user in the current group | [Link](rooms/groups-endpoints/removeleader.md)                 |
| `/api/v1/groups.removeModerator`   | Removes moderator role from a user in a group        | [Link](rooms/groups-endpoints/removemoderator.md)              |
| `/api/v1/groups.removeOwner`       | Removes owner role from a user in a group            | [Link](rooms/groups-endpoints/removeowner.md)                  |
| `/api/v1/groups.rename`            | Changes the name of the private group                | [Link](rooms/groups-endpoints/rename.md)                       |
| `/api/v1/groups.roles`             | Retrieves user's roles in the private group          | [Link](rooms/groups-endpoints/roles.md)                        |
| `/api/v1/groups.setAnnouncement`   | Sets a group's announcement                          | [Link](rooms/groups-endpoints/setannouncement.md)              |
| `/api/v1/groups.setCustomFields`   | Sets private group's custom fields                   | [Link](rooms/groups-endpoints/setcustomfields.md)              |
| `/api/v1/groups.setDescription`    | Sets a private group's description                   | [Link](rooms/groups-endpoints/setdescription.md)               |
| `/api/v1/groups.setPurpose`        | Sets a private group's purpose                       | [Link](rooms/groups-endpoints/setpurpose.md)                   |
| `/api/v1/groups.setReadOnly`       | Sets whether the room is read-only or not            | [Link](rooms/groups-endpoints/setreadonly.md)                  |
| `/api/v1/groups.setTopic`          | Sets a private group's topic                          | [Link](rooms/groups-endpoints/settopic.md)                      |
| `/api/v1/groups.setType`           | Sets the type of room this group will be              | [Link](rooms/groups-endpoints/settype.md)                       |
| `/api/v1/groups.unarchive`         | Unarchives a private group                            | [Link](rooms/groups-endpoints/unarchive.md)                     |
| `/api/v1/groups.setEncrypted`      | Sets the encryption for a group                       | [Link](rooms/groups-endpoints/group-set-encrypted.md)           |
| `/api/v1/groups.convertToTeam`     | Converts a private group to a team                    | [Link](rooms/groups-endpoints/group-converttoteam.md)           |

### Channels

These methods apply to public channels only. Use `groups.*` methods for private channels.

| URL                               | Short Description                                     | Details Page                                                     |
| --------------------------------- | ----------------------------------------------------- | ---------------------------------------------------------------- |
| `/api/v1/channels.addAll`         | Adds all users to a channel                           | [Link](rooms/channels-endpoints/addall.md)                        |
| `/api/v1/channels.addLeader`      | Gives Leader role to a user in the current channel    | [Link](rooms/channels-endpoints/addleader.md)                     |
| `/api/v1/channels.addModerator`   | Gives moderator role to a user in a channel           | [Link](rooms/channels-endpoints/addmoderator.md)                  |
| `/api/v1/channels.addOwner`       | Gives owner role to a user in a channel               | [Link](rooms/channels-endpoints/addowner.md)                      |
| `/api/v1/channels.anonymousread`  | Gets messages in public channels for an anonymous user | [Link](rooms/channels-endpoints/anonymousread.md)                 |
| `/api/v1/channels.archive`        | Archives a channel                                    | [Link](rooms/channels-endpoints/archive.md)                       |
| `/api/v1/channels.close`          | Removes a channel from a user's list                  | [Link](rooms/channels-endpoints/close.md)                         |
| `/api/v1/channels.counters`       | Retrieves channel counters                            | [Link](rooms/channels-endpoints/counters.md)                      |
| `/api/v1/channels.create`         | Creates a new channel                                 | [Link](rooms/channels-endpoints/create.md)                        |
| `/api/v1/channels.delete`         | Removes a channel                                     | [Link](rooms/channels-endpoints/delete.md)                        |
| `/api/v1/channels.getAllUserMentionsByChannel` | Retrieves mentions of a channel           | [Link](rooms/channels-endpoints/getallusermentionsbychannel.md)   |
| `/api/v1/channels.files`          | Retrieves files from a channel                        | [Link](rooms/channels-endpoints/files.md)                         |
| `/api/v1/channels.getIntegrations`| Retrieves channel integrations                        | [Link](rooms/channels-endpoints/getintegrations.md)               |
| `/api/v1/channels.history`        | Retrieves messages from a channel                     | [Link](rooms/channels-endpoints/history.md)                       |
| `/api/v1/channels.info`           | Gets channel information                              | [Link](rooms/channels-endpoints/info.md)                          |
| `/api/v1/channels.invite`         | Adds a user to a channel                              | [Link](rooms/channels-endpoints/invite.md)                        |
| `/api/v1/channels.join`           | Joins a channel                                       | [Link](rooms/channels-endpoints/join.md)                          |
| `/api/v1/channels.kick`           | Removes a user from a channel                         | [Link](rooms/channels-endpoints/kick.md)                          |
| `/api/v1/channels.leave`          | Removes the caller from a channel                     | [Link](rooms/channels-endpoints/leave.md)                         |
| `/api/v1/channels.list`           | Retrieves all channels from the server                | [Link](rooms/channels-endpoints/list.md)                          |
| `/api/v1/channels.list.joined`    | Retrieves joined channels of the calling user         | [Link](rooms/channels-endpoints/list-joined.md)                   |
| `/api/v1/channels.members`        | Retrieves all channel users                            | [Link](rooms/channels-endpoints/members.md)                       |
| `/api/v1/channels.messages`       | Retrieves all channel messages                         | [Link](rooms/channels-endpoints/messages.md)                      |
| `/api/v1/channels.moderators`     | Lists all moderators of a channel                      | [Link](rooms/channels-endpoints/moderators.md)                    |
| `/api/v1/channels.online`         | Lists all online users of a channel                    | [Link](rooms/channels-endpoints/online.md)                        |
| `/api/v1/channels.open`           | Adds the channel back to the user's list               | [Link](rooms/channels-endpoints/open.md)                          |
| `/api/v1/channels.removeleader`   | Removes Leader role from a user in the current channel | [Link](rooms/channels-endpoints/removeleader.md)                  |
| `/api/v1/channels.removeModerator`| Removes moderator role from a user in a channel        | [Link](rooms/channels-endpoints/removemoderator.md)               |
| `/api/v1/channels.removeOwner`    | Removes owner role from a user in a channel            | [Link](rooms/channels-endpoints/removeowner.md)                   |
| `/api/v1/channels.rename`         | Changes a channel's name                              | [Link](rooms/channels-endpoints/rename.md)                        |
| `/api/v1/channels.roles`          | Gets user's roles in the channel                       | [Link](rooms/channels-endpoints/roles.md)                         |
| `/api/v1/channels.setAnnouncement`| Sets a channel's announcement                         | [Link](rooms/channels-endpoints/setannouncement.md)               |
| `/api/v1/channels.setCustomFields`| Sets a channel's custom fields                         | [Link](rooms/channels-endpoints/setcustomfields.md)               |
| `/api/v1/channels.setDefault`     | Sets a channel's default status                        | [Link](rooms/channels-endpoints/setdefault.md)                    |
| `/api/v1/channels.setDescription` | Sets a channel's description                           | [Link](rooms/channels-endpoints/setdescription.md)                |
| `/api/v1/channels.setJoinCode`    | Sets the channel's join code                           | [Link](rooms/channels-endpoints/setjoincode.md)                   |
| `/api/v1/channels.setPurpose`     | Sets a channel's purpose                               | [Link](rooms/channels-endpoints/setpurpose.md)                    |
| `/api/v1/channels.setReadOnly`    | Sets whether a channel is read-only or not             | [Link](rooms/channels-endpoints/setreadonly.md)                   |
| `/api/v1/channels.setTopic`       | Sets a channel's topic                                 | [Link](rooms/channels-endpoints/settopic.md)                      |
| `/api/v1/channels.setType`        | Sets the type of room the channel should be            | [Link](rooms/channels-endpoints/settype.md)                       |
| `/api/v1/channels.unarchive`      | Unarchives a channel                                   | [Link](rooms/channels-endpoints/unarchive.md)                     |
| `/api/v1/channels.convertToTeam`  | Converts channel to team                              | [Link](rooms/channels-endpoints/convert-channel-to-team.md)       |

### Room

| Url                                          | Short Description                                      | Details Page                                                            |
| -------------------------------------------- | ------------------------------------------------------ | ----------------------------------------------------------------------- |
| `/api/v1/rooms.adminRooms`                     | Retrieves all rooms (requires special permission).       | [Link](rooms/rooms-endpoints/adminrooms.md)                        |
| `/api/v1/rooms.cleanHistory`                   | Cleans up a room's history, requires special permission. | [Link](rooms/rooms-endpoints/clean-room-history.md)                |
| `/api/v1/rooms.createDiscussion`               | Creates a new discussion.                              | [Link](rooms/rooms-endpoints/creatediscussion.md)                  |
| `/api/v1/rooms.favorite`                       | Favorites/Unfavorites room.                            | [Link](rooms/rooms-endpoints/favorite-unfavourite-a-room.md)       |
| `/api/v1/rooms.get`                            | Retrieves rooms.                                       | [Link](rooms/rooms-endpoints/get-rooms.md)                         |
| `/api/v1/rooms.getDiscussions`                 | Retrieves room's discussions.                          | [Link](rooms/rooms-endpoints/getdiscussions.md)                    |
| `/api/v1/rooms.info`                           | Gets info from a room.                                 | [Link](rooms/rooms-endpoints/info.md)                               |
| `/api/v1/rooms.leave`                          | Leaves a room.                                         | [Link](rooms/rooms-endpoints/leave-room.md)                         |
| `/api/v1/rooms.saveNotification`               | Sets the notification settings of a specific channel.  | [Link](rooms/rooms-endpoints/save-room-notification.md)            |
| `/api/v1/rooms.upload/:rid`                    | Uploads a message with the attached file.              | [Link](rooms/rooms-endpoints/upload-file-to-a-room.md)              |
| `/api/v1/rooms.adminRooms.getRoom`             | Retrieves all admin rooms                              | [Link](rooms/rooms-endpoints/get-admin-rooms.md)                    |
| `/api/v1/rooms.autocomplete.channelAndPrivate` | Autocompletes private channel                          | [Link](rooms/rooms-endpoints/autocomplete-private-channel.md)       |
| `/api/v1/rooms.autocomplete.availableForTeams` | Autocompletes room name available for conversion to team | [Link](rooms/rooms-endpoints/room-name-autocomplete-for-team.md)    |
| `/api/v1/rooms.saveRoomSettings`               | Save the settings of a room                            | [Link](rooms/rooms-endpoints/save-room-settings.md)                 |
| `/api/v1/rooms.changeArchivationState`         | Change the Archive state of a room.                    | [Link](rooms/rooms-endpoints/change-archivation-state.md)           |
| `/api/v1/rooms.export`                         | Export room to a file or email.                        | [Link](rooms/rooms-endpoints/export-room.md)                        |

### Teams

| Url                              | Short Description                                         | Details Page                                                                                                                                |
| -------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/teams.list`             | Lists the public and private teams the caller is part of. | [Link](rooms/teams-endpoints/list-of-teams-of-caller.md)                                                                           |
| `/api/v1/teams.listAll`          | Lists all of the teams and their information.             | [Link](rooms/teams-endpoints/list-all-teams-with-info.md)                                                                          |
| `/api/v1/teams.create`           | Creates a new team.                                       | [Link](rooms/teams-endpoints/create-a-new-team.md)                                                                                 |
| `/api/v1/teams.convertToChannel` | Converts team to channel.                                 | [Link](rooms/teams-endpoints/convert-team-to-channel.md) |
| `/api/v1/teams.addRooms`         | Adds rooms to the team.                                   | [Link](rooms/teams-endpoints/add-rooms-to-a-team.md)                                                                               |
| `/api/v1/teams.removeRoom`       | Removes a room from a team.                               | [Link](rooms/teams-endpoints/remove-a-room-from-team.md)                                                                           |
| `/api/v1/teams.updateRoom`       | Updates a room from a team, limited to permissions.       | [Link](rooms/teams-endpoints/update-room-from-a-team.md)                                                                           |
| `/api/v1/teams.listRooms`        | Lists all rooms of the team.                              | [Link](rooms/teams-endpoints/list-rooms-of-a-team.md)                                                                              |
| `/api/v1/teams.listRoomsOfUser`  | Lists only the team's rooms the user has joined.          | [Link](rooms/teams-endpoints/list-rooms-of-user-of-a-team.md)                                                                      |
| `/api/v1/teams.members`          | Retrieves all team members.                               | [Link](rooms/teams-endpoints/get-teams-members.md)                                                                                 |
| `/api/v1/teams.addMembers`       | Adds members to the team.                                 | [Link](rooms/teams-endpoints/add-members.md)                                                                                       |
| `/api/v1/teams.updateMember`     | Updates a team member's roles, limited to permissions.    | [Link](rooms/teams-endpoints/update-a-teams-member.md)                                                                             |
| `/api/v1/teams.removeMember`     | Removes a member from a team.                             | [Link](rooms/teams-endpoints/remove-member-from-team.md)                                                                           |
| `/api/v1/teams.leave`            | Leaves a team.                                            | [Link](rooms/teams-endpoints/leave-a-team.md)                                                                                      |
| `/api/v1/teams.info`             | Gets a team's information.                                | [Link](rooms/teams-endpoints/get-teams-info.md)                                                                                    |
| `/api/v1/teams.delete`           | Removes a team.                                           | [Link](rooms/teams-endpoints/delete-a-team.md)                                                                                     |
| `/api/v1/teams.autocomplete`     | Lists the teams whose names match a given pattern.        | [Link](rooms/teams-endpoints/autocomplete-team.md)                                                                                 |
| `/api/v1/teams.update`           | Updates an existing team (name and type).                 | [Link](rooms/teams-endpoints/update-a-team.md)                                                                                     |

### Directory

<<<<<<< HEAD
| Url                   | Short Description                                                   | Details Page                                                                                                                             |
| --------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/directory`   | Searches by all users and channels available on the server.         | [Link](rooms/directory.md)
=======
| Url                 | Short Description                                       | Details Page                                                |
| ------------------- | ------------------------------------------------------- | ----------------------------------------------------------- |
| `/api/v1/directory` | Searches by all users and channels available on server. | [Link](core-endpoints/miscellaneous-endpoints/directory.md) |
>>>>>>> cb2e849029c17201e655aebfabf96ec9fabad300

## Messaging

### Chat

| URL                                    | Short Description                                                | Details Page                                                                                                                     |
| -------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/chat.delete`                  | Deletes an existing chat message.                                | [Link](messaging/chat-endpoints/delete.md)                                                                                  |
| `/api/v1/chat.followMessage`           | Follows an existing chat message.                                | [Link](messaging/chat-endpoints/follow-message.md)                                                                          |
| `/api/v1/chat.getDeletedMessages`      | Retrieves the deleted messages from a specific date.             | [Link](messaging/chat-endpoints/getdeletedmessages.md)                                                                      |
| `/api/v1/chat.getDiscussions`          | Retrieves the discussions of a room.                             | [Link](messaging/chat-endpoints/getdiscussions.md)                                                                          |
| `/api/v1/chat.getMentionedMessages`    | Retrieves the mentioned messages.                                | [Link](messaging/chat-endpoints/getmentionedmessages.md)                                                                    |
| `/api/v1/chat.getMessage`              | Retrieves a single chat message.                                 | [Link](messaging/chat-endpoints/getmessage.md)                                                                              |
| `/api/v1/chat.getMessageReadReceipts`  | Retrieves message read receipts.                                 | [Link](messaging/chat-endpoints/getmessagereadreceipts.md)                                                                  |
| `/api/v1/chat.getPinnedMessages`       | Retrieves pinned messages from a room.                           | [Link](messaging/chat-endpoints/getpinnedmessages.md)                                                                       |
| `/api/v1/chat.getSnippetedMessages`    | Retrieves snippet messages.                                      | [Link](messaging/chat-endpoints/getsnippetedmessages.md)                                                                    |
| `/api/v1/chat.getSnippetedMessageById` | Retrieves snippet message by id.                                 | [Link](messaging/chat-endpoints/getsnippetedmessagebyid.md)                                                                 |
| `/api/v1/chat.getStarredMessages`      | Retrieves the starred messages.                                  | [Link](messaging/chat-endpoints/getstarredmessages.md)                                                                      |
| `/api/v1/chat.getThreadMessages`       | Retrieves thread's messages.                                     | [Link](messaging/chat-endpoints/getthreadmessages.md)                                                                       |
| `/api/v1/chat.getThreadsList`          | Retrieves channel's threads.                                     | [Link](messaging/chat-endpoints/getthreadslist.md)                                                                          |
| `/api/v1/chat.ignoreUser`              | Ignores abuser from a chat.                                      | [Link](messaging/chat-endpoints/ignoreuser.md)                                                                              |
| `/api/v1/chat.pinMessage`              | Pins a chat message to the message's channel.                    | [Link](messaging/chat-endpoints/pinmessage.md)                                                                              |
| `/api/v1/chat.postMessage`             | Posts a new chat message.                                        | [Link](messaging/chat-endpoints/postmessage.md)                                                                             |
| `/api/v1/chat.react`                   | Sets/unsets the user's reaction to an existing chat message.     | [Link](messaging/chat-endpoints/chat-message-reactions.md)                                                                  |
| `/api/v1/chat.reportMessage`           | Reports a message.                                               | [Link](messaging/chat-endpoints/reportmessage.md)                                                                           |
| `/api/v1/chat.search`                  | Searches for messages in a channel.                              | [Link](messaging/chat-endpoints/search-message.md)                                                                          |
| `/api/v1/chat.starMessage`             | Stars a chat message for the authenticated user.                 | [Link](messaging/chat-endpoints/starmessage.md)                                                                             |
| `/api/v1/chat.sendMessage`             | Sends a new chat message.                                        | [Link](messaging/chat-endpoints/send-message.md)                                                                            |
| `/api/v1/chat.syncThreadMessages`      | Retrieves synced thread's messages.                              | [Link](messaging/chat-endpoints/syncthreadmessages.md)                                                                      |
| `/api/v1/chat.syncThreadsList`         | Retrieves thread's synced channel threads.                       | [Link](messaging/chat-endpoints/syncthreadslist.md)                                                                         |
| `/api/v1/chat.unfollowMessage`         | Unfollows an existing chat message.                              | [Link](messaging/chat-endpoints/unfollowmessage.md)                                                                         |
| `/api/v1/chat.unPinMessage`            | Removes the pinned status of the provided chat message.          | [Link](messaging/chat-endpoints/unpinmessage.md)                                                                            |
| `/api/v1/chat.unStarMessage`           | Removes the star on the chat message for the authenticated user. | [Link](messaging/chat-endpoints/unstarmessage.md)                                                                           |
| `/api/v1/chat.update`                  | Updates the text of the chat message.                            | [Link](messaging/chat-endpoints/message-update.md)                                                                          |
| `/api/v1/chat.syncMessages`            | Syncs messages                                                   | [Link](messaging/chat-endpoints/sync-messages.md) |

### DM/IM

| URL                          | Short Description                                | Details Page                                             |
| ---------------------------- | ------------------------------------------------ | -------------------------------------------------------- |
| `/api/v1/im.delete`          | Removes a direct message session                 | [Link](messaging/chat-endpoints/delete.md)               |
| `/api/v1/im.close`           | Removes a direct message from the list of messages | [Link](messaging/im-endpoints/close.md)                  |
| `/api/v1/im.counters`        | Gets counters of direct messages                  | [Link](core-endpoints/im-endpoints/counters.md)          |
| `/api/v1/im.create`          | Creates a direct message session                  | [Link](core-endpoints/im-endpoints/create.md)            |
| `/api/v1/im.history`         | Retrieves messages from a direct message          | [Link](core-endpoints/im-endpoints/history.md)           |
| `/api/v1/im.files`           | Retrieves a list of files from a direct message   | [Link](core-endpoints/im-endpoints/files.md)             |
| `/api/v1/im.members`         | Retrieves participants of a direct message        | [Link](core-endpoints/im-endpoints/members.md)           |
| `/api/v1/im.messages`        | Retrieves messages from specific direct messages  | [Link](core-endpoints/im-endpoints/messages.md)          |
| `/api/v1/im.messages.others` | Retrieves messages from any direct message        | [Link](core-endpoints/im-endpoints/messages-others.md)   |
| `/api/v1/im.list`            | Lists direct messages the caller is part of       | [Link](core-endpoints/im-endpoints/list.md)              |
| `/api/v1/im.list.everyone`   | Lists all direct messages to the caller           | [Link](core-endpoints/im-endpoints/list-everyone.md)     |
| `/api/v1/im.open`            | Adds direct message back to the list of messages  | [Link](core-endpoints/im-endpoints/open.md)              |
| `/api/v1/im.setTopic`        | Sets a direct message topic                       | [Link](core-endpoints/im-endpoints/settopic.md)          |

{% hint style="info" %}
From version 0.50.0 and on, you can call the methods using `dm` instead of `im`.
{% endhint %}

## Omnichannel

### Livechat

#### Livechat Agent

| Url                               | Short Description                              | Details Page                                                                                                                                |
| --------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/agent.info/:rid/:token` | Retrieves the current omnichannel agent data   | [Link](omnichannel/livechat-endpoints/livechat-agent/agent.md)      |
| `livechat/agent.next/:token`      | Retrieves the data of the next available agent | [Link](omnichannel/livechat-endpoints/livechat-agent/next-agent) |

#### Livechat Configuration

| Url               | Short Description                                                         | Details Page                                                                                                                      |
| ----------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/config` | Retrieves LiveChat widget configuration info and additional visitor data. | [Link](omnichannel/livechat-endpoints/livechat-config) |

#### Livechat Contacts

| Url                          | Short Description                                   | Details Page                                                                                                                                                    |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `omnichannel/contact`        | Registers a guest user as a new omnichannel contact | [Link](omnichannel/livechat-endpoints/livechat-contact/register-omnichannel-contact) |
| `omnichannel/contact`        | Retrieves a contact information                     | [Link](omnichannel/livechat-endpoints/livechat-contact/omnichannel-fetch-contact)    |
| `omnichannel/contact.search` | Searches a contact information                      | [Link](omnichannel/livechat-endpoints/livechat-contact/omnichannel-search-contact)   |

#### Livechat Custom Field

| Url                           | Short Description                             | Details Page                                                                                                                                                            |
| ----------------------------- | --------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/custom.field`       | Sends a custom field                          | [Link](omnichannel/livechat-endpoints/custom-fields/send-a-livechat-custom-field)            |
| `livechat/custom.fields`      | Sends an array of custom field                | [Link](omnichannel/livechat-endpoints/custom-fields/send-an-array-of-livechat-custom-fields) |
| `livechat/custom-fields`      | Retrieves a list of omnichannel custom fields | [Link](omnichannel/livechat-endpoints/custom-fields/list-livechat-custom-fields)             |
| `livechat/custom-fields/:_id` | Retrieves info about a custom field           | [Link](omnichannel/livechat-endpoints/custom-fields/get-info-about-a-custom-field)           |

#### Livechat Message

| Url                              | Short Description                      | Details Page                                                                                                                                                      |
| -------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/message`               | Sends a new omnichannel message        | [Link](omnichannel/livechat-endpoints/livechat-message/livechat-send-new-message)      |
| `livechat/message/:_id`          | Retrieves a specific message           | [Link](omnichannel/livechat-endpoints/livechat-message/retrieve-a-livechat-message)    |
| `livechat/message/:_id`          | Updates an omnichannel message         | [Link](omnichannel/livechat-endpoints/livechat-message/update-a-livechat-message)      |
| `livechat/message/:_id`          | Removes an omnichannel message         | [Link](omnichannel/livechat-endpoints/livechat-message/remove-a-livechat-message)      |
| `livechat/messages.history/:rid` | Retrieves omnichannel messages history | [Link](omnichannel/livechat-endpoints/livechat-message/load-livechat-messages-history) |
| `livechat/messages`              | Sends array of messages                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-message/send-an-array-of-messages)                            |

#### Livechat Offline Message

| Url                        | Short Description                                   | Details Page                                                                                                                               |
| -------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/offline.message` | Sends an offline message when no agent is available | [Link](omnichannel/livechat-endpoints/livechat-offline-message) |

#### Livechat Page Visited

| Url                     | Short Description                                                    | Details Page                                                                                                                                      |
| ----------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/page.visited` | Retrieves the pages your omnichannel user navigated on your website. | [Link](omnichannel/livechat-endpoints/livechat-page-visited/send-visitor-navigation-history) |

#### Livechat Room

| Url                      | Short Description                                                 | Details Page                                                                                                                                           |
| ------------------------ | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/room`          | GetRetrievesthe omnichannel room data or open a new conversation. | [Link](omnichannel/livechat-endpoints/livechat-room/livechat-room-info)     |
| `livechat/room.close`    | Closes an omnichannel conversation                                | [Link](omnichannel/livechat-endpoints/livechat-room/livechat-room-close)    |
| `livechat/room.transfer` | Transfers an omnichannel conversation                             | [Link](omnichannel/livechat-endpoints/livechat-room/livechat-room-transfer) |
| `livechat/room.forward`  | Chatbot agent forwards the chat to a human agent                  | [Link](omnichannel/livechat-endpoints/livechat-room/livechat-room-forward)  |
| `livechat/room.visitor`  | Updates room visitor's information                                | [Link](omnichannel/livechat-endpoints/livechat-room/change-room-visitor)    |

#### Livechat Transcript

| Url                   | Short Description              | Details Page                                                                                                                          |
| --------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transcript` | Requests a Livechat transcript | [Link](omnichannel/livechat-endpoints/livechat-transcript) |

#### Livechat Transfer

| Url                              | Short Description                           | Details Page                                                                                                                        |
| -------------------------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transfer.history/:rid` | Retrieves the conversation transfer history | [Link](omnichannel/livechat-endpoints/livechat-transfer) |

#### Livechat Visitor

| Url                            | Short Description                        | Details Page                                                                                                                                                 |
| ------------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/visitor`             | Registers a new visitor                  | [Link](omnichannel/livechat-endpoints/visitor/register-a-new-livechat-visitor)    |
| `livechat/visitor/:token`      | Retrieves a visitor                      | [Link](omnichannel/livechat-endpoints/visitor/retrieve-a-visitor-data)            |
| `livechat/visitor/:token`      | Deletes a visitor                        | [Link](omnichannel/livechat-endpoints/visitor/delete-a-visitor)                   |
| `livechat/visitor/:token/room` | Retrieves open conversation of a visitor | [Link](omnichannel/livechat-endpoints/visitor/get-open-conversation-of-a-visitor) |
| `livechat/visitor.status`      | Sets visitor status                      | [Link](omnichannel/livechat-endpoints/visitor/set-visitor-status)                 |

#### Livechat Agent Stats

| Url                                  | Short Description                            | Details Page                                                                                                                             |
| ------------------------------------ | -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/agents/:agentId/departments`                             | Returns all the departments associated with an agent  | [Link](omnichannel/livechat-endpoints/agents/agents-departments)                  |
| `api/v1/livechat/analytics/agents/average-service-time`                   | Retrieves average service time per agent        | [Link](omnichannel/livechat-endpoints/agents/agents-average-service-time)        |
| `api/v1/livechat/analytics/agents/total-service-time`                     | Retrieves total service time sorted by agent     | [Link](omnichannel/livechat-endpoints/agents/agents-total-service-time)          |
| `api/v1/livechat/analytics/agents/available-for-service-history`           | Retrieves a list of agents and their available time for the provided time frame | [Link](omnichannel/livechat-endpoints/agents/agents-available-for-service-history) |

#### Livechat Appearance

| Url                          | Short Description                                   | Details Page                                                                                              |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/appearance` | Retrieves LiveChat widget settings about appearance | [Link](omnichannel/livechat-endpoints/appearance) |

#### Livechat Business Hours

| Url                                   | Short Description                                           | Details Page                                                                                                                      |
| ------------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/business-hour`       | Retrieves all the information of a particular business hour | [Link](omnichannel/livechat-endpoints/business-hours/business-hour-info)  |
| `api/v1/livechat/business-hours.list` | Retrieves a list of existing business hours                 | [Link](omnichannel/livechat-endpoints/business-hours/business-hours-list) |

#### Livechat Dashboards

| Url                                                                   | Short Description                                       | Details Page                                                                                                                            |
| --------------------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/analytics/dashboards/conversation-totalizers`        | Retrieves conversation totalizers for a department      | [Link](omnichannel/livechat-endpoints/dashboards/conversation-totalizers)       |
| `api/v1/livechat/analytics/dashboards/agents-productivity-totalizers` | Retrieves agent productivity totalizer for a department | [Link](omnichannel/livechat-endpoints/dashboards/agent-productivity-totalizers) |
| `api/v1/livechat/analytics/dashboards/chats-totalizers`               | Retrieves chat totalizers for a department              | [Link](omnichannel/livechat-endpoints/dashboards/chat-totalizers)               |
| `api/v1/livechat/analytics/dashboards/productivity-totalizers`        | Retrieves productivity totalizers for a department      | [Link](omnichannel/livechat-endpoints/dashboards/productivity-totalizers)       |
| `api/v1/livechat/analytics/dashboards/charts/chats`                   | Retrieves chats chart for a department                  | [Link](omnichannel/livechat-endpoints/dashboards/chats-chart)                   |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-agent`         | Retrieves chats per agent for a department chart        | [Link](omnichannel/livechat-endpoints/dashboards/chats-per-agent-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/agents-status`           | Retrieves agent's statuses chart                        | [Link](omnichannel/livechat-endpoints/dashboards/agents-statuses-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-department`    | Retrieves chats per department chart                    | [Link](omnichannel/livechat-endpoints/dashboards/chats-per-department-chart)    |
| `api/v1/livechat/analytics/dashboards/charts/timings`                 | Retrieves timing charts                                 | [Link](omnichannel/livechat-endpoints/dashboards/timings-charts)                |

#### Livechat Departments

| Url                                                                | Short Description                                             | Details Page                                                                                                                                  |
| ------------------------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/department`                                       | Retrieves a list of departments                               | [Link](omnichannel/livechat-endpoints/livechat-department/get-a-list-of-departments)           |
| `api/v1/livechat/department`                                       | Registers a new department                                    | [Link](omnichannel/livechat-endpoints/livechat-department/register-a-new-department)           |
| `api/v1/livechat/department/:_id`                                  | Retrieves a department's info                                 | [Link](omnichannel/livechat-endpoints/livechat-department/get-info-about-a-department)         |
| `api/v1/livechat/department/:_id`                                  | Updates a department                                          | [Link](omnichannel/livechat-endpoints/livechat-department/update-a-department)                 |
| `api/v1/livechat/department/:_id`                                  | Removes a department                                          | [Link](omnichannel/livechat-endpoints/livechat-department/remove-a-department)                 |
| `api/v1/livechat/department.autocomplete`                          | Autocompletes department name                                 | [Link](omnichannel/livechat-endpoints/livechat-department/department-autocomplete)             |
| `api/v1/livechat/department/:departmentId/agents`                  | Retrieves agents of a specific department                     | [Link](omnichannel/livechat-endpoints/livechat-department/retrieve-agents-of-a-department)     |
| `api/v1/livechat/department/:departmentId/agents`                  | Updates agents of a department                                | [Link](omnichannel/livechat-endpoints/livechat-department/update-agents-of-a-department)       |
| `api/v1/livechat/department.listByIds`                             | Retrieves a list of departments by an array of department ids | [Link](omnichannel/livechat-endpoints/livechat-department/listing-departments-by-ids)          |
| `api/v1/livechat/departments.available-by-unit/:unitId`            | Retrieves departments available by unit Id                    | [Info](omnichannel/livechat-endpoints/livechat-department/departments-available-by-unit-id)                           |
| `api/v1/livechat/analytics/departments/amount-of-chats`            | Retrieves the number of incoming chats                        | [Info](omnichannel/livechat-endpoints/livechat-department/amount-of-chat)                                             |
| `api/v1/livechat/analytics/departments/average-service-time`       | Retrieves average service time                                | [Info](omnichannel/livechat-endpoints/livechat-department/average-service-time-by-department)                         |
| `api/v1/livechat/analytics/departments/average-chat-duration-time` | Retrieves average chats duration                              | [Info](omnichannel/livechat-endpoints/livechat-department/average-chat-duration-time-by-department)                   |
| `api/v1/livechat/analytics/departments/total-service-time`         | Retrieves total service time                                  | [Info](omnichannel/livechat-endpoints/livechat-department/total-service-time-by-department)                           |
| `api/v1/livechat/analytics/departments/average-waiting-time`       | Retrieves avg waiting time                                    | [Info](omnichannel/livechat-endpoints/livechat-department/average-waiting-time-by-department)                         |
| `api/v1/livechat/analytics/departments/total-transferred-chats`    | Retrieves total transferred chats                             | [Info](omnichannel/livechat-endpoints/livechat-department/total-transferred-chat-by-department)                       |
| `api/v1/livechat/analytics/departments/total-abandoned-chats`      | Retrieves abandoned chats                                     | [Info](omnichannel/livechat-endpoints/livechat-department/total-abandoned-chats-by-department) |
| `api/v1/livechat/analytics/departments/percentage-abandoned-chats` | Retrieves percentage of abandoned chats                       | [Info](omnichannel/livechat-endpoints/livechat-department/percentage-of-abandoned-chats-by-department)                |

#### Livechat Inquiries

| Url                                  | Short Description                        | Details Page                                                                                                                |
| ------------------------------------ | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/inquiries.list`     | Lists all of the open livechat inquiries | [Link](omnichannel/livechat-endpoints/livechat-inquiries/inquiries-list)     |
| `api/v1/livechat/inquiries.take`     | Takes an open inquiry                    | [Link](omnichannel/livechat-endpoints/livechat-inquiries/take-inquiry)       |
| `api/v1/livechat/inquiries.queued`   | Lists queued inquiries                   | [Link](omnichannel/livechat-endpoints/livechat-inquiries/inquiries-queued)   |
| `api/v1/livechat/inquiries.getOne`   | Gets one inquiry by room id              | [Link](omnichannel/livechat-endpoints/livechat-inquiries/inquiry-get-one)    |
| `api/v1/livechat/inquiry.prioritize` | Sets the priority of an inquiry          | [Link](omnichannel/livechat-endpoints/livechat-inquiries/inquiry-prioritize) |
| `api/v1/livechat/inquiry.setSLA`     | Set SLA to an inquiry.                   | [Link](livechat-endpoints/livechat-inquiries/set-sla-to-inquiry.md)                                                         |

#### Livechat Integrations

| Url                                     | Short Description                        | Details Page                                                                                                |
| --------------------------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/integrations.settings` | Retrieves a list of integration settings | [Link](omnichannel/livechat-endpoints/livechat-integrations.md) |

#### Livechat Queue

| Url                     | Short Description          | Details Page                                                                                                  |
| ----------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/queue` | Retrieves the queued chats | [Link](omnichannel/livechat-endpoints/livechat-queue) |

#### Livechat Rooms

| Url                                  | Short Description                            | Details Page                                                                                                     |
| ------------------------------------ | -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/rooms`              | Retrieves a list of livechat rooms           | [Link](omnichannel/livechat-endpoints/livechat-rooms/livechat-rooms-list.md)                                                 |
| `api/v1/livechat/room/:rid/priority` | Set the priority of a Livechat room.         | [Link](omnichannel/livechat-endpoints/livechat-rooms/set-livechat-room-priority.md)                                          |
| `api/v1/livechat/room/:rid/priority` | Remove the priority set to a Livechat room.  | [Link](omnichannel/livechat-endpoints/livechat-rooms/remove-livechat-room-priority.md)                                       |
| `api/v1/livechat/room.onHold`        | Puts an active livechat conversation on hold | [Link](omnichannel/livechat-endpoints/rooms/room-onhold) |

#### Livechat SMS

| Url                                     | Short Description | Details Page                                                                                                       |
| --------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/sms-incoming/:service` | Receives SMS      | [Link](omnichannel/livechat-endpoints/sms-incoming-twilio) |

#### Livechat Triggers

| Url                             | Short Description                  | Details Page                                                                                                                      |
| ------------------------------- | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/triggers`      | Lists all Livechat triggers        | [Link](omnichannel/livechat-endpoints/triggers/get-the-livechat-triggers) |
| `api/v1/livechat/triggers/:_id` | Retrieves a Livechat Trigger by id | [Link](omnichannel/livechat-endpoints/triggers/get-a-livechat-trigger)    |

#### Livechat Upload

| Url                           | Short Description | Details Page |
| ----------------------------- | ----------------- | ------------ |
| `api/v1/livechat/upload/:rid` | post              |              |

#### Livechat Users

| Url                                | Short Description                   | Details Page                                                                                                                         |
| ---------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/users/:type`      | Gets a list of agents or managers   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/users)     |
| `api/v1/livechat/users/:type`      | Registers a new agent or manager    | [Link](omnichannel/livechat-endpoints/livechat-users/register-new-agent-or-manager.md)   |
| `api/v1/livechat/users/:type/:_id` | Gets info about an agent or manager | [Link](omnichannel/livechat-endpoints/livechat-users/get-info-of-an-agent-or-manager) |
| `api/v1/livechat/users/:type/:_id` | Removes an agent or manager         | [Link](omnichannel/livechat-endpoints/livechat-users/remove-an-agent-or-manager)      |

#### Livechat Visitors

| Url                                                                    | Short Description                           | Details Page                                                                                                                                  |
| ---------------------------------------------------------------------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/visitors.info`                                        | Retrieves visitor info by ID                | [Link](omnichannel/livechat-endpoints/visitors/visitor-info-by-id)                    |
| `api/v1/livechat/visitors.pagesVisited/:roomId`                        | Retrieves pages visited by livechat visitor | [Link](omnichannel/livechat-endpoints/visitors/get-pages-visited-by-livechat-visitor) |
| `api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId` | Retrieves livechat visitor's chat history   | [Link](omnichannel/livechat-endpoints/visitors/get-livechat-visitors-chat-history)    |
| `api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId` | Searches a visitor's chat                   | [Link](omnichannel/livechat-endpoints/visitors/search-a-visitors-chat)                |
| `api/v1/livechat/visitors.autocomplete`                                | Autocompletes visitor's name                | [Link](omnichannel/livechat-endpoints/visitors/visitor-autocomplete)                  |
| `api/v1/livechat/visitors.search`                                      | Searches the visitor by the term            | [Link](omnichannel/livechat-endpoints/visitors/visitors-search)                       |

#### Livechat Monitors

| Url                                  | Short Description | Details Page                                                  |
| ------------------------------------ | ----------------- | ------------------------------------------------------------- |
| `api/v1/livechat/monitors`           | List all monitors | [Link](livechat-endpoints/livechat-monitors/get-monitors.md)  |
| `api/v1/livechat/monitors/:username` | Get a Monitor     | [Link](livechat-endpoints/livechat-monitors/get-a-monitor.md) |

#### Livechat Priorities

| Url                                      | Short Description   | Details Page                                                                               |
| ---------------------------------------- | ------------------- | ------------------------------------------------------------------------------------------ |
| `api/v1/livechat/priorities`             | Get priorities      | [Link](livechat-endpoints/livechat-priorities/priorities-older-versions/get-priorities.md) |
| `api/v1/livechat/priorities/:priorityId` | Get a priority      | [Link](livechat-endpoints/livechat-priorities/priorities-older-versions/get-a-priority.md) |
| `api/v1/livechat/priorities/:priorityId` | Update the priority | [Link](livechat-endpoints/livechat-priorities/update-priority.md)                          |
| `api/v1/livechat/priorities.reset`       | Reset the priority  | [Link](livechat-endpoints/livechat-priorities/reset-priorities.md)                         |

#### Livechat Tags

| Url                    | Short Description        | Details Page                                          |
| ---------------------- | ------------------------ | ----------------------------------------------------- |
| `api/v1/livechat/tags` | Retrieves a list of tags | [Link](livechat-endpoints/livechat-tags/get-tags.md)  |
| `livechat/tags/:tagId` | Get a tag.               | [Link](livechat-endpoints/livechat-tags/get-a-tag.md) |

#### Livechat Units

| Url                                      | Short Description           | Details Page                                                           |
| ---------------------------------------- | --------------------------- | ---------------------------------------------------------------------- |
| `api/v1/livechat/units`                  | Create unit                 | [Link](livechat-endpoints/livechat-units/create-unit.md)               |
| `api/v1/livechat/units`                  | List all omnichannel units. | [Link](livechat-endpoints/livechat-units/get-units.md)                 |
| `api/v1/livechat/units/:unitId`          | Retrieves details of a unit | [Link](livechat-endpoints/livechat-units/get-a-unit.md)                |
| `api/v1/livechat/units/:unitId/monitors` | List unit monitors          | [Link](livechat-endpoints/livechat-units/get-list-of-unit-monitors.md) |
| `api/v1/livechat/units/:id`              | Update Unit by Id           | [Link](livechat-endpoints/livechat-units/update-unit.md)               |
| `api/v1/livechat/units/:id`              | Delete unit using ID        | [Link](livechat-endpoints/livechat-units/delete-unit.md)               |

### Voice Channel

| URL                                                     | Description                                     | Details Page                                                                                                               |
| ------------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `/v1/connector.extension.getRegistrationInfoByUserId`    | Get registration information by ID              | [Link](./#voip-registration-information)                                                                                   |
| `/api/v1/voip/queues.getSummary`                         | Get VoIP query summary data                     | [Link](./#voip-query-summary)                                                                                              |
| `/api/v1/voip/queues.getSummary`                         | Get VoIP query summary data                     | [Link](./#voip-query-summary)                                                                                              |
| `/api/v1/voip/queues.getSummary`                         | Get VoIP queue membership data                  | [Link](omnichannel/voice-channel-endpoints/voice-channel-queue-membership/get-call-center-queue-membership-information.md) |
| `/v1/voip/queues.getMembershipSubscription`              | Get VoIP queue membership subscription data     | [Link](./#voip-queue-membership)                                                                                           |
| `/v1/voip/queues.getMembershipSubscription`              | Get VoIP queue membership subscription data     | [Link](./#voip-queue-membership)                                                                                           |
| `v1/voip/queues.getMembershipSubscription`               | Get the VoIP queue membership subscription data | [Link](./#voip-queue-membership)                                                                                           |
| `api/v1/livechat/visitor`                                | Create a VoIP visitor                           | [Link](./#create-visitor)                                                                                                  |
| `/api/v1/voip/events`                                    | Send VoIP events                                | [Link](./#send-voip-events)                                                                                                |
| `/api/v1/omnichannel/extension`                          | Retrieve VoIP extension information             | [Link](./#fetch-voip-extensions)                                                                                           |
| `/api/v1/omnichannel/extensions?count=10&offset=10`      | Retrieve VoIP extensions                        | [Link](./#fetch-voip-extensions)                                                                                           |
| `/v1/omnichannel/agent/extension`                        | Create, update and delete VoIP extension        | [Link](./#agent-extensions)                                                                                                |
| `/api/v1/voip/managementServer/checkConnection?host&port&username&password` | Check management server connection status       | [Link](./#check-management-server-connection)                                                                              |
| `/api/v1/voip/callServer/checkConnection?websocketUrl=wss://omni-asterisk.dev.rocket.chat/ws` | Check call server connection status             | [Link](./#check-call-server-connection)                                                                                    |
| `/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba&agentId=6vHSSqdBHdm2R4gfi` | Create VoIP room                                | [Link](./#create-voip-room)                                                                                                |
| `/api/v1/voip/events`                                    | Retrieve VoIP room information by ID            | [Link](./#fetch-voip-room-by-id)                                                                                           |
| `/api/v1/voip/room.clos`                                 | Close the VoIP conversation                     | [Link](./#close-voip-room)                                                                                                 |

### Canned Response

| URL                             | Short Description         | Details Page                                                      |
| ------------------------------- | ------------------------- | ----------------------------------------------------------------- |
| `/api/v1/canned-responses`      | Create a canned response. | [Link](omnichannel/canned-responses/create-a-canned-response.md)  |
| `/api/v1/canned-responses`      | Update a canned response. | [Link](omnichannel/canned-responses/update-a-canned-response.md)  |
| `/api/v1/canned-responses/:_id` | Get a canned response     | [Link](omnichannel/canned-responses/get-a-canned-response.md)     |
| `/api/v1/canned-responses`      | List all canned responses | [Link](omnichannel/canned-responses/list-all-canned-responses.md) |
| `/api/v1/canned-responses.get`  | Get user canned responses | [Link](omnichannel/canned-responses/get-canned-responses.md)      |
| `/api/v1/canned-responses`      | Remove a canned response  | [Link](omnichannel/canned-responses/remove-canned-response.md)    |

## Integrations

### Integration

| Url                            | Short Description                               | Details Page                                          |
| ------------------------------ | ----------------------------------------------- | ----------------------------------------------------- |
| `/api/v1/integrations.create`  | Creates an integration.                         | [Link](integrations/integration-endpoints/create.md)  |
| `/api/v1/integrations.get`     | Gets an integration.                            | [Link](integrations/integration-endpoints/get.md)     |
| `/api/v1/integrations.history` | Lists all history of the specified integration. | [Link](integrations/integration-endpoints/history.md) |
| `/api/v1/integrations.list`    | Lists all of the integrations.                  | [Link](integrations/integration-endpoints/list.md)    |
| `/api/v1/integrations.remove`  | Removes an integration.                         | [Link](integrations/integration-endpoints/remove.md)  |
| `/api/v1/integrations.update`  | Updates an integration.                         | [Link](integrations/integration-endpoints/update.md)  |

### Webdav

| URL                            | Short Description                    | Details Page                                                                                                            |
| ------------------------------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/webdav.getMyAccounts` | Retrieves the user's webdav accounts | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/webdav-endpoint/getmyaccounts) |

### OAuth App

| Url                      | Short Description                             | Details Page                                           |
| ------------------------ | --------------------------------------------- | ------------------------------------------------------ |
| `/api/v1/oauth-apps.get` | Retrieves an OAuth App by id or client id.     | [Link](integrations/oauthapps-endpoints/get.md)        |
| `/api/v1/oauth-apps.list`| Retrieves a list of OAuth Apps.                | [Link](integrations/oauthapps-endpoints/list.md)       |

## Notifications

### Banners

| URL                       | Short Description                                      | Details Page                                                                                                                 |
| ------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/banners/:id`     | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banner-by-id) |
| `/api/v1/banners`         | Gets the banners to be shown to the authenticated user | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/get-banners)      |
| `/api/v1/banners.dismiss` | Dismisses a banner                                     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/banners/dismiss-a-banner) |

### Push

| Url                  | Short Description                   | Details Page                                                                                                                                       |
| -------------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/push.token` | Saves push token.                   | [Link](notifications/push-token-endpoints/push-token.md)                                                                                           |
| `/api/v1/push.token` | Removes push token.                 | [Link](notifications/push-token-endpoints/deletepushtoken.md)                                                                                      |
| `/api/v1/push.get`   | Get push notification for a message | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/push-token-endpoints/Get%20push%20notification) |

## Content Management

### Assets

| URL                           | Short Description                 | Details Page                                                                                 |
| ----------------------------- | --------------------------------- | -------------------------------------------------------------------------------------------- |
| `/api/v1/assets.setAsset`     | Sets an asset image by name.      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/setasset)     |
| `/api/v1/assets.unsetAsset`   | Unsets an asset by name.          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/assets/unsetasset)   |


### Custom Emoji

| Url                           | Short Description                          | Details Page                                                                                                                                      |
| ----------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/emoji-custom.all`    | Retrieves all custom emojis                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-emoji-endpoints/list-all-custom-emojis) |
| `/api/v1/emoji-custom.list`   | Retrieves an updated list of custom emojis | [Link](content-management/custom-emoji-endpoints/list-custom-emojis.md)                                                                           |
| `/api/v1/emoji-custom.create` | Creates new custom emoji.                  | [Link](content-management/custom-emoji-endpoints/create-new-custom-emoji.md)                                                                      |
| `/api/v1/emoji-custom.delete` | Delete an existent custom emoji.           | [Link](content-management/custom-emoji-endpoints/delete-custom-emoji.md)                                                                          |
| `/api/v1/emoji-custom.update` | Updates an existent custom emoji.          | [Link](content-management/custom-emoji-endpoints/update-a-custom-emoji.md)                                                                        |

### Custom Sounds

| URL                          | Short Description                  | Details Page                                                                                                                                                     |
| ---------------------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-sounds.list` | Retrieves a list of custom sounds. | [Link](https://app.gitbook.com/@rocket-chat/s/rocket-chat-developer/\~/drafts/-MgSmy428hAP1znS6g3V/api/rest-api/endpoints/team-collaboration/custom-sounds/list) |

### Custom User Status

| URL                                 | Short Description                         | Details Page                                                                                                                                                    |
| ----------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/custom-user-status.list`   | Lists all available custom user's status. | [Link](content-management/custom-user-status-endpoints/list.md)                                                                                                 |
| `/api/v1/custom-user-status.create` | Creates custom user status                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/create-custom-user-status)      |
| `/api/v1/custom-user-status.delete` | Deletes a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/delete-custom-user-status)      |
| `/api/v1/custom-user-status.update` | Updates a custom user status              | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/custom-user-status-endpoints/update-custom-user-status-type) |

## Statistics

### Stats

| URL                       | Short Description         | Details Page                                                                                                                            |
| ------------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/statistics`      | Retrieves statistics      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics)      |
| `/api/v1/statistics.list` | Retrieves statistics list | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/stats-endpoints/get-statistics-list) |

### Engagement Dashboard

#### Users Engagement Dashboard Endpoints

| Url                                                | Short Description                                      | Details Page                                                                                     |
| -------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `/api/v1/engagement-dashboard/users/new-users`      | List new users during a specific period                | [Link](statistics/engagement-dashboard/users-engagement-dashboard/list-new-users.md)             |
| `/api/v1/engagement-dashboard/users/active-users`   | List active users in the workspace                     | [Link](statistics/engagement-dashboard/users-engagement-dashboard/list-active-users.md)          |
| `/api/v1/engagement-dashboard/users/users-by-time-of-the-day-in-a-week` | List users by hours at a particular time of the day in a week | [Link](statistics/engagement-dashboard/users-engagement-dashboard/list-user-by-time-of-the-day.md) |
| `/api/v1/engagement-dashboard/users/chat-busier/hourly-data` | Get hourly data when chat is busier              | [Link](statistics/engagement-dashboard/users-engagement-dashboard/get-hourly-data-when-chat-is-busier.md) |
| `/api/v1/engagement-dashboard/users/chat-busier/weekly-data` | Get weekly data when chat is busier              | [Link](statistics/engagement-dashboard/users-engagement-dashboard/get-weekly-data-when-chat-is-busier.md) |

#### Messages Engagement Dashboard Endpoints

| URL                                                         | Short Description                                        | Details Page                                                                                         |
| ----------------------------------------------------------- | -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `/api/v1/engagement-dashboard/messages/messages-sent`        | Get number of daily messages sent during a period         | [Link](statistics/engagement-dashboard/messages-engagement-dashboard/get-messages-sent.md)         |
| `/api/v1/engagement-dashboard/messages/origin`               | Get origin of messages sent during a period               | [Link](statistics/engagement-dashboard/messages-engagement-dashboard/get-origin-of-message-sent.md) |
| `/api/v1/engagement-dashboard/messages/top-five-popular-channels` | Get top 5 popular channels by message count          | [Link](statistics/engagement-dashboard/messages-engagement-dashboard/get-the-most-popular-channels.md) |

#### Channels Engagement Dashboard Endpoints

| URL                                       | Short Description                                  | Details Page                                                                             |
| ----------------------------------------- | -------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `api/v1/engagement-dashboard/channels/list` | Get all channels and the number of messages in each | [Link](statistics/engagement-dashboard/channels-engagement-dashboard/get-channels.md) |

### Subscription

| Url                            | Short Description                      | Details Page                                                          |
| ------------------------------ | -------------------------------------- | --------------------------------------------------------------------- |
| `/api/v1/subscriptions.get`    | Retrieves all subscriptions.           | [Link](statistics/subscriptions-endpoints/get-all-subscriptions.md)   |
| `/api/v1/subscriptions.getOne` | Retrieves the subscription by room Id. | [Link](statistics/subscriptions-endpoints/get-subscription-room.md)   |
| `/api/v1/subscriptions.read`   | Marks a room as read.                  | [Link](statistics/subscriptions-endpoints/mark-channel-as-read.md)    |
| `/api/v1/subscriptions.unread` | Marks messages as unread.              | [Link](statistics/subscriptions-endpoints/mark-messages-as-unread.md) |

## Settings

### Settings

You can get and update the settings via the REST API, only if you have permission to.

| Url                              | Short Description                             | Details Page                                                      |
| -------------------------------- | --------------------------------------------- | ----------------------------------------------------------------- |
| `/api/v1/settings`               | Lists all private settings.                   | [Link](settings/settings-endpoints/get-private-settings.md)       |
| `/api/v1/settings.public`        | Lists all public settings.                    | [Link](settings/settings-endpoints/get-public-settings.md)        |
| `/api/v1/settings.oauth`         | Returns list of all available oauth services. | [Link](settings/settings-endpoints/get-all-oauth.md)              |
| `/api/v1/service.configurations` | Lists all service configurations.             | [Link](settings/settings-endpoints/get-service-configurations.md) |
| `/api/v1/settings/:_id`          | Retrieves a setting.                          | [Link](settings/settings-endpoints/get-setting-by-id.md)          |
| `/api/v1/settings/:_id`          | Updates a setting.                            | [Link](settings/settings-endpoints/update-setting.md)             |

### Cloud

| URL                            | Short Description              | Details Page                                              |
| ------------------------------ | ------------------------------ | --------------------------------------------------------- |
| `/api/v1/cloud.manualRegister` | Manually registers a workspace | [Link](settings/cloud-endpoints/cloud-manual-register.md) |

### DNS

| URL                       | Short Description                                      | Details Page                                        |
| ------------------------- | ------------------------------------------------------ | --------------------------------------------------- |
| `/api/v1/dns.resolve.srv` | Resolves DNS srv records (SRV records) for a hostname  | [Link](settings/dns-endpoints/dns-resolve-txt-1.md) |
| `/api/v1/dns.resolve.txt` | Resolves DNS text records (TXT records) for a hostname | [Link](settings/dns-endpoints/dns-resolve-txt.md)   |

### E2E

| URL                                       | Short Description                                               | Details Page                                                                                                                                        |
| ----------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/e2e.fetchMyKeys`                 | Retrieves E2E keys of logged in user                            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/fetch-your-e2e-keys)               |
| `/api/v1/e2e.getUsersOfRoomWithoutKey`    | Retrieves Users Of Room Without E2E Key                         | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/get-users-of-room-without-e2e-key) |
| `/api/v1/e2e.setRoomKeyID`                | Sets the end-to-end encryption key ID for a room                | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-room-e2e-key)                  |
| `/api/v1/e2e.setUserPublicAndPrivateKeys` | Sets the end-to-end encryption keys for the authenticated user. | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/set-users-key)                     |
| `/api/v1/e2e.updateGroupKey`              | Updates the end-to-end encryption key for a user in a room.     | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/e2e-endpoints/update-user-e2e-key-in-room)       |

### Imports

| URL                                 | Short Description              | Details Page                                                       |
| ----------------------------------- | ------------------------------ | ------------------------------------------------------------------ |
| `/api/v1/uploadImportFile`          | Upload import file.            | [Link](settings/import-endpoints/upload-import-file.md)            |
| `/api/v1/downloadPublicImportFile`  | Download public import file.   | [Link](settings/import-endpoints/download-public-import-file.md)   |
| `/api/v1/startImport`               | Start import.                  | [Link](settings/import-endpoints/start-import.md)                  |
| `/api/v1/getImportFileData`         | Get file data of an upload.    | [Link](settings/import-endpoints/get-import-file-data.md)          |
| `/api/v1/getImportProgress`         | Get the progress of an import. | [Link](settings/import-endpoints/get-import-progress.md)           |
| `/api/v1/getLatestImportOperations` | Get latest import operations   | [Link](settings/import-endpoints/get-latest-import-operations.md)  |
| `/api/v1/downloadPendingFiles`      | Download pending files         | [Link](settings/import-endpoints/download-pending-files.md)        |
| `/api/v1/downloadPendingAvata`      | Download pending avatars       | [Link](settings/import-endpoints/download-pending-avatars.md)      |
| `/api/v1/getCurrentImportOperation` | Gets current import operations | [Link](settings/import-endpoints/get-current-import-operations.md) |

### Instances

| URL                     | Short Description   | Details Page                                                                                                                          |
| ----------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/instances.get` | Retrieves instances | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/instances-endpoints/get-instances) |

### Federation

| Url                                    | Short Description                           | Details Page              |
|----------------------------------------|---------------------------------------------|---------------------------|
| `api/v1/federation/addServerByUser`    | Adds a server to search public rooms later   | [Link](add-server.md)     |
| `api/v1/federation/listServersByUser`  | Retrieves all the server names saved by the user | [Link](list-servers.md) |
| `api/v1/federation/removeServerByUser` | Remove a server name                         | [Link](remove-server.md)  |
| `api/v1/federation/searchPublicRooms`  | Returns all the public room given a server name | [Link](search-public-rooms.md) |
| `api/v1/joinExternalPublicRoom`        | Joins an External public Matrix room         | [Link](join-external-public-room.md) |

### Device Management

| URL                     | Short Description                                | Details Page                                                              |
| ----------------------- | ------------------------------------------------ | ------------------------------------------------------------------------- |
| `/api/v1/sessions/list` | Retrieves all sessions of the authenticated user | [Link](settings/device-management-endpoints/get-current-user-sessions.md) |

## Miscellaneous

### Auto Translate

| URL                                           | Short Description                               | Details Page                                                                                                        |
| --------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/autotranslate.getSupportedLanguages` | Gets the supported languages by auto-translate. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/getsupportedlanguages) |
| `/api/v1/autotranslate.saveSettings`          | Saves some settings about auto-translate.       | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/savesettings)          |
| `/api/v1/autotranslate.translateMessage`      | Translates the message.                         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration/autotranslate/translatemessage)      |

### Commands

| URL                        | Short Description                                                         | Details Page                                                                                                                     |
| -------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/commands.get`     | Retrieves the specification of the slash command.                         | [Link](miscellaneous/commands-endpoints/get-slash-commands.md)                                                                   |
| `/api/v1/commands.list`    | Lists all available slash commands.                                       | [Link](miscellaneous/commands-endpoints/list.md)                                                                                 |
| `/api/v1/commands.run`     | Executes a slash command in the specified room.                           | [Link](miscellaneous/commands-endpoints/execute-a-slash-command.md)                                                              |
| `/api/v1/commands.preview` | Retrieves the preview data for the command and executes the preview item. | [Link](miscellaneous/commands-endpoints/preview.md)                                                                              |
| `/api/v1/commands.preview` | Executes command's preview item                                           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/commands/execute-commands-preview-item) |

### Email Inbox

| URL                                  | Short Description                    | Details Page                                                                                                                                             |
| ------------------------------------ | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/email-inbox.list`           | Retrieves mail Inbox list            | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-list)               |
| `/api/v1/email-inbox`                | Sets the email inbox for your server | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/set-email-inbox)                |
| `/api/v1/email-inbox/:_id`           | Retrieves email Inbox by id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/email-inbox-by-id)              |
| `/api/v1/email-inbox/:_id`           | Delete email inbox using id          | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/delete-email-inbox-by-id)       |
| `/api/v1/email-inbox.search`         | Searches email inbox by address      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/search-email-inbox-by-email)    |
| `/api/v1/email-inbox.send-test/:_id` | Sends test email to email inbox      | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/email-inbox-endpoints/send-test-email-to-email-inbox) |

### Invite

| Url                           | Short Description                                                         | Details Page                                                                                                                             |
| ----------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/findOrCreateInvite`  | Created a new Invite or returns an existing one with the same parameters. | [Link](miscellaneous/invite-endpoints/findorcreateinvite.md)                                                                             |
| `/api/v1/listInvites`         | Lists all of the invite tokens.                                           | [Link](miscellaneous/invite-endpoints/listinvites.md)                                                                                    |
| `/api/v1/removeInvite/:_id`   | Deletes an invite from the server.                                        | [Link](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/invite-endpoints/delete-invite-by-id) |
| `/api/v1/useInviteToken`      | Reports to the server that an invite token was used.                      | [Link](miscellaneous/invite-endpoints/report-use-invite-token.md)                                                                        |
| `/api/v1/validateInviteToken` | Checks if an invite token is valid.                                       | [Link](miscellaneous/invite-endpoints/validateinvitetoken.md)                                                                            |

### Licenses

| Url                            | Short Description                           | Details Page                                   |
|--------------------------------|---------------------------------------------|------------------------------------------------|
| `/api/v1/licenses.get`        | Gets all registered licenses.               | [Link](miscellaneous/licenses/get-licenses.md)               |
| `/api/v1/licenses.isEnterprise` | Confirm if workspace has enterprise license. | [Link](miscellaneous/licenses/confirm-enterprise-license.md) |
| `licenses.maxActiveUsers`      | Get maximum active users.                   | [Link](miscellaneous/licenses/get-maximum-active-user.md)   |

### Video conference

| URL                                             | Short Description                                           | Details Page                                                                                                                              |
| ----------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `/api/v1/video-conference/jitsi.update-timeout` | Updates the timeout of Jitsi video conference in a channel. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/team-collaboration-endpoints/video-conference-endpoints/jitsi-update-timeout) |



### Install Private Apps&#x20;

<table><thead><tr><th width="248.5388701110575">URL</th><th width="290.3333333333333">Short Description</th><th>Details Page</th></tr></thead><tbody><tr><td><code>/api/apps</code></td><td>Install a private app via URL</td><td><a href="miscellaneous/install-private-apps.md">Link</a></td></tr></tbody></table>

### WhatsApp

| Description                                       | Details Page                                                                     |
| ------------------------------------------------- | -------------------------------------------------------------------------------- |
| WhatsApp Business API integration for Rocket.Chat | [Link](miscellaneous/whatsapp-endpoints/whatsapp-omnichannel-integration-api.md) |
| Send a template message.                          | [Link](miscellaneous/whatsapp-endpoints/template-message.md)                     |
