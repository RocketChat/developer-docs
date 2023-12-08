# Get Profile Information

Quick information about the authenticated user.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/me</code></td><td><a href="./"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/me
```

## Example Response

```json
{
  "_id": "aobEdbYhXfu5hkeqG",
  "name": "Example User",
  "emails": [
    {
      "address": "example@example.com",
      "verified": true
    }
  ],
  "status": "offline",
  "statusConnection": "offline",
  "username": "example",
  "utcOffset": 0,
  "active": true,
  "roles": [
      "user",
      "admin"
  ],
  "settings": {
        "preferences": {
            "enableAutoAway": false,
            "idleTimeoutLimit": 300,
            "desktopNotificationDuration": 0,
            "audioNotifications": "mentions",
            "desktopNotifications": "mentions",
            "mobileNotifications": "mentions",
            "unreadAlert": true,
            "useEmojis": true,
            "convertAsciiEmoji": true,
            "autoImageLoad": true,
            "saveMobileBandwidth": true,
            "collapseMediaByDefault": false,
            "hideUsernames": false,
            "hideRoles": false,
            "hideFlexTab": false,
            "hideAvatars": false,
            "roomsListExhibitionMode": "category",
            "sidebarViewMode": "medium",
            "sidebarHideAvatar": false,
            "sidebarShowUnread": false,
            "sidebarShowFavorites": true,
            "sendOnEnter": "normal",
            "messageViewMode": 0,
            "emailNotificationMode": "all",
            "roomCounterSidebar": false,
            "newRoomNotification": "door",
            "newMessageNotification": "chime",
            "muteFocusedConversations": true,
            "notificationsSoundVolume": 100
        }
  },
    "customFields": {
        "twitter": "@userstwi"
    },
  "avatarUrl": "http://localhost:3000/avatar/test",
  "customFields": {
      "twitter": "@userstwi"
  },
  "success": true
}
```

{% hint style="info" %}
The `customFields` parameter will not be returned if it does not exist on the server.
{% endhint %}

## Change Log

| Version | Description                            |
| ------- | -------------------------------------- |
| 1.0.0   | Added `avatarUrl` property to response |
| 0.68.0  | Added `customFields` property.         |
| 0.48.0  | Added                                  |
