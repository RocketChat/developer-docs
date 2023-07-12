---
description: Set preferences for the running user or provided userId
---

# Set Preferences

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `/api/v1/`users.setPreferences | `yes`         | `POST`      |

## Payload

| Argument                        | Type          | Required | Description                                                                                                                                                                                   |
| ------------------------------- | ------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `userId`                        | `String`      | Optional | The unique identifier for the user to change. Must have _edit-other-user-info_ for changing other users preferences. If userId is not provided, it will set preferences for the running user. |
| `data.language`                 | `String`      | Optional | The preferred language for the user. Example : "`En`"                                                                                                                                         |
| `data.newRoomNotification`      | `String`      | Optional | New room notification. Example : "`door`".                                                                                                                                                    |
| `data.newMessageNotification`   | `String`      | Optional | New message notification.                                                                                                                                                                     |
| `data.muteFocusedConversations` | Boolean       | Optional | A Boolean value indicates whether the user has enabled the option to mute focused conversations.                                                                                              |
| `data.clockMode`                | `Number`      | Optional | The valid display formats for the clock.                                                                                                                                                      |
| `data.useEmojis`                | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to use emojis.                                                                                                              |
| `data.convertAsciiEmoji`        | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to convert ASCII emojis.                                                                                                    |
| `data.saveMobileBandwidth`      | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to save mobile bandwidth.                                                                                                   |
| `data.collapseMediaByDefault`   | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to collapse media by default.                                                                                               |
| `data.autoImageLoad`            | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.emailNotificationMode`    | `String`      | Optional | The preferred mode for Email notification. Example : "`mentions`".                                                                                                                            |
| `data.unreadAlert`              | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.notificationsSoundVolume` | `Number`      | Optional | The default sound volume for the notification. Example : "`100`".                                                                                                                             |
| `data.desktopNotifications`     | `String`      | Optional | The default desktop notifications.                                                                                                                                                            |
| `data.pushNotifications`        | `String`      | Optional | The mobile push notification.                                                                                                                                                                 |
| `data.enableAutoAway`           | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.highlights`               | `String List` | Optional | The message highlights section.                                                                                                                                                               |
| `data.messageViewMode`          | `Number`      | Optional | The preferred view mode for the messages.                                                                                                                                                     |
| `data.hideUsernames`            | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.hideRoles`                | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.displayAvatars`           | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.hideFlexTab`              | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.sendOnEnter`              | `String`      | Optional | The value indicates whether "SendonEnter" option is enabled.                                                                                                                                  |
| `data.idleTimeLimit`            | `Number`      | Optional | The default limit for the idle time. Example: 300                                                                                                                                             |
| `data.sidebarShowFavorites`     | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |
| `data.sidebarShowUnread`        | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to show unread messages in the sidebar.                                                                                     |
| `data.sidebarSortby`            | `String`      | Optional | To sort in alphabetical or by activity.                                                                                                                                                       |
| `data.sidebarViewMode`          | `String`      | Optional | The view mode the sidebar. Example : "`condensed`".                                                                                                                                           |
| `data.sidebarDisplayAvatar`     | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to display avatar in the sidebar.                                                                                           |
| `data.sidebarGroupByType`       | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option to show the grouped values in the sidebar.                                                                                  |
| `data.`dontAskAgainList         |               |          |                                                                                                                                                                                               |
| `data.muteFocusedConversations` | `Boolean`     | Optional | A Boolean value indicates whether the user has enabled the option.                                                                                                                            |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.setPreferences \
     -d '{ "userId": "BsNr28znDkG8aeo7W", "data": { } }'
```

## Example Result

```
// "settings": {
        "preferences": {
            "enableAutoAway": true,
            "idleTimeLimit": 300,
            "desktopNotificationRequireInteraction": false,
            "desktopNotifications": "default",
            "pushNotifications": "all",
            "unreadAlert": false,
            "useEmojis": true,
            "convertAsciiEmoji": true,
            "autoImageLoad": true,
            "saveMobileBandwidth": true,
            "collapseMediaByDefault": false,
            "hideUsernames": false,
            "hideRoles": false,
            "hideFlexTab": false,
            "displayAvatars": true,
            "sidebarGroupByType": true,
            "sidebarViewMode": "condensed",
            "sidebarDisplayAvatar": true,
            "sidebarShowUnread": true,
            "sidebarSortby": "activity",
            "showMessageInMainThread": false,
            "sidebarShowFavorites": true,
            "sendOnEnter": "normal",
            "messageViewMode": 0,
            "emailNotificationMode": "mentions",
            "newRoomNotification": "door",
            "newMessageNotification": "chime",
            "muteFocusedConversations": true,
            "notificationsSoundVolume": 100,
            "enableMessageParserEarlyAdoption": false,
            "mobileNotifications": "default",
            "desktopNotificationDuration": 0,
            "dontAskAgainList": [],
            "highlights": [],
            "language": "en"
        }
    },
```

| Version | Description                                             |
| ------- | ------------------------------------------------------- |
| 2.3.0   | Added `desktopNotificationRequireInteraction` property. |
