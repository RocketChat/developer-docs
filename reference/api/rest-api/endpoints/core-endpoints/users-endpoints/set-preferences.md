# Set Preferences

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `/api/v1/users.saveUserPreferences` | `yes`         | `POST`      |

## Payload

| Argument                   | Type      | Required | Description                                                                                                  |
| -------------------------- | --------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| `user`                     | `String`  | Required | The unique identifier for the user.                                                                          |
| `language`                 | `String`  | Required | The preferred language for the user. Example : "`En`"                                                        |
| `newRoomNotification`      | `String`  | Required | New room notification. Example : "`door`".                                                                   |
| `newMessageNotification`   | `String`  | Required | New message notification.                                                                                    |
| `muteFocusedConversations` | Boolean   | Required | A Boolean value indicates whether the user has enabled the option to mute focused conversations.             |
| `clockMode`                | `Number`  | Required | The valid display formats for the clock.                                                                     |
| `useEmojis`                | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option to use emojis.                             |
| `convertAsciiEmoji`        | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option to convert ASCII emojis.                   |
| `saveMobileBandwidth`      | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option to save mobile bandwidth.                  |
| `collapseMediaByDefault`   | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option to collapse media by default.              |
| `autoImageLoad`            | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `emailNotificationMode`    | `String`  | Required | The preferred mode for Email notification. Example : "`mentions`".                                           |
| `unreadAlert`              | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `notificationsSoundVolume` | `Number`  | Required | The default sound volume for the notification. Example : "`100`".                                            |
| `desktopNotifications`     | `String`  | Required | The default desktop notifications.                                                                           |
| `pushNotifications`        | `String`  | Required | The mobile push notification.                                                                                |
| `enableAutoAway`           | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `highlights`               | `String`  | Required | The message highlights section.                                                                              |
| `messageViewMode`          | `Number`  | Required | The preferred view mode for the messages.                                                                    |
| `hideUsernames`            | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `hideRole`s                | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `displayAvatars`           | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `hideFlexTab`              | `Boolean` | Required | A Boolean value indicates whether the user has enabled the option.                                           |
| `sendOnEnter`              | `String`  | Required | The value indicates whether "SendonEnter" option is enabled.                                                 |
| `idleTimeLimit`            | `Number`  | Required | The default limit for the idle time. Example: 300                                                            |
| `sidebarShowFavorites`     | `Boolean` | Optional | A Boolean value indicates whether the user has enabled the option.                                           |
| `sidebarShowUnread`        | `Boolean` | Optional | A Boolean value indicates whether the user has enabled the option to show unread messages in the sidebar.    |
| `sidebarSortby`            | `String`  | Optional | To sort in alphabetical or by activity.                                                                      |
| `sidebarViewMode`          | `String`  | Optional | The view mode the sidebar. Example : "`condensed`".                                                          |
| `sidebarDisplayAvatar`     | `Boolean` | Optional | A Boolean value indicates whether the user has enabled the option to display avatar in the sidebar.          |
| `sidebarGroupByType`       | `Boolean` | Optional | A Boolean value indicates whether the user has enabled the option to show the grouped values in the sidebar. |
| dontAskAgainList           |           |          |                                                                                                              |
| `muteFocusedConversations` | `Boolean` | Optional | A Boolean value indicates whether the user has enabled the option.                                           |

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
