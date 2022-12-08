---
description: Gets user data of the authenticated user
---

# Get user data

| URL          | Requires Auth | HTTP Method |
| ------------ | ------------- | ----------- |
| `/api/v1/me` | `Yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request GET 'http://localhost:3000/api/v1/me' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "_id": "d26x6zSkaPSe5gCyy",
    "services": {
        "password": {
            "exists": true
        },
        "email2fa": {
            "enabled": false
        }
    },
    "emails": [
        {
            "address": "",
            "verified": true
        }
    ],
    "status": "offline",
    "active": true,
    "_updatedAt": "2021-10-14T10:26:28.038Z",
    "roles": [
        "user",
        "admin",
        "livechat-agent",
        "livechat-manager"
    ],
    "name": "Renata",
    "username": "renata",
    "requirePasswordChange": false,
    "avatarOrigin": "gravatar",
    "statusConnection": "offline",
    "utcOffset": -3,
    "statusLivechat": "available",
    "statusDefault": "online",
    "settings": {
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
    "language": "en",
    "banners": {
        "alert-5ef278548cb114eda1a9c6e2": {
            "id": "alert-5ef278548cb114eda1a9c6e2",
            "priority": 10,
            "title": "Maintenance Reminder",
            "text": "Saturday 2020-06-27 at 20﹕00 UTC we will be performing Maintenance. Click for more info",
            "textArguments": [],
            "modifiers": [],
            "link": "https://forums.rocket.chat/t/scheduled-maintenance-saturday-2020-06-27/7327",
            "read": true
        },
        "alert-5ef6d2f58cb114eda1eb34ff": {
            "id": "alert-5ef6d2f58cb114eda1eb34ff",
            "priority": 10,
            "title": "Maintenance Rescheduled",
            "text": "New Date - 2020-07-03 at 23﹕00 UTC ",
            "textArguments": [],
            "modifiers": [],
            "link": "https://forums.rocket.chat/t/scheduled-maintenance-friday-2020-07-03/7327",
            "read": true
        },
        "alert-5f10e9638cb114eda1a443d1": {
            "id": "alert-5f10e9638cb114eda1a443d1",
            "priority": 10,
            "title": "Notice",
            "text": "Be sure to register your server before July 31, 2020 to keep your mobile notifications flowing.",
            "textArguments": [],
            "modifiers": [],
            "link": "https://forums.rocket.chat/t/enforcing-registration-requirement-to-utilize-push-gateway/7545",
            "read": true
        },
        "alert-5fcc1f02f5204d09050943d2": {
            "id": "alert-5fcc1f02f5204d09050943d2",
            "priority": 10,
            "title": "Attn: Important Security fix",
            "text": "For all installations using SAML Please upgrade as soon as possible.  3.9.1 / 3.8.3 / 3.7.3 / 2.4.13 / 1.3.4 / 0.74.4",
            "textArguments": [],
            "modifiers": [],
            "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/3.9.1",
            "read": true
        },
        "alert-5fdd5b24f5204d0905f9bd4d": {
            "id": "alert-5fdd5b24f5204d0905f9bd4d",
            "priority": 10,
            "title": "Security Alert",
            "text": "Important Cross-Site-Scripting (XSS) security fix. Please upgrade as soon as possible. 3.9.3 / 3.8.4 / 3.7.4 / 2.4.14 / 1.3.5",
            "textArguments": [],
            "modifiers": [],
            "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/3.9.3",
            "read": true
        },
        "alert-601374b9f5204d0905": {
            "id": "alert-601374b9f5",
            "priority": 10,
            "title": "Security Alert",
            "text": "Critical security hotfix for Live Chat available in our latest releases 3.10.5, 3.9.7, 3.8.8. Please upgrade as soon as possible.",
            "textArguments": [],
            "modifiers": [],
            "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/3.10.5",
            "read": true
        },
        "someAppInInvalidState": {
            "id": "someAppInInvalidState",
            "priority": 10,
            "title": "Warning",
            "text": "There is one or more apps in an invalid state. Click here to review.",
            "modifiers": [
                "danger"
            ],
            "link": "/admin/apps",
            "read": true
        }
    },
    "statusText": "",
    "email": "",
    "avatarUrl": "https://multiverse.rocket.chat/avatar/reb",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
