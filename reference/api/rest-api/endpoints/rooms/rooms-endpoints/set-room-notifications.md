# Set Room Notifications

Sets the notification settings of a specific room.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.saveNotification</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="204.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>5of4weEXaH7yncxz9</code></td><td>The channel's id</td></tr><tr><td><code>notifications</code><mark style="color:red;"><code>*</code></mark></td><td><code>"notifications": {...}</code></td><td>The object that contains the following parameters.</td></tr><tr><td><code>desktopNotifications</code></td><td><code>nothing</code></td><td><p>The value for desktop notifications. The options are:</p><ul><li><code>nothing</code></li><li><code>mentions</code></li><li><code>all</code></li><li><code>default</code></li></ul></td></tr><tr><td><code>disableNotifications</code></td><td><code>0</code></td><td><p>The value to disable/enable channel's notifications. </p><p>The options are:</p><ul><li><code>0</code></li><li><code>1</code></li></ul></td></tr><tr><td><code>emailNotifications</code></td><td><code>nothing</code></td><td><p>The value for email notifications. </p><p>The options are:</p><ul><li><code>nothing</code></li><li><code>mentions</code></li><li><code>all</code></li><li><code>default</code></li></ul></td></tr><tr><td><code>audioNotifications</code></td><td><code>nothing</code></td><td><p>The value for audio notifications. </p><p>The options are:</p><ul><li><code>nothing</code></li><li><code>mentions</code></li><li><code>all</code></li><li><code>default</code></li></ul></td></tr><tr><td><code>notifications.mobilePushNotifications</code></td><td><code>nothing</code></td><td><p>The value for mobile push notifications. </p><p>The options are:</p><ul><li><code>nothing</code></li><li><code>mentions</code></li><li><code>all</code></li><li><code>default</code></li></ul></td></tr><tr><td><code>audioNotificationValue</code></td><td><code>beep</code></td><td>The value for audio notification sound.</td></tr><tr><td><code>desktopNotificationDuration</code></td><td><code>0</code></td><td>The value for desktop notification duration.</td></tr><tr><td><code>unreadAlert</code></td><td><code>nothing</code></td><td><p>The value for unread alerts notifications. </p><p>The options are:</p><ul><li><code>nothing</code></li><li><code>mentions</code></li><li><code>all</code></li><li><code>default</code></li></ul></td></tr><tr><td><code>hideUnreadStatus</code></td><td><code>0</code></td><td><p>The value to disable/enable number of unread messages. </p><p>The options are:</p><ul><li><code>0</code></li><li><code>1</code></li></ul></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.saveNotification \
     -d '{
          "roomId": "5of4weEXaH7yncxz9", 
          "notifications" :{ 
               "desktopNotifications": "all", 
               "disableNotifications": "0", 
               "emailNotifications": "nothing", 
               "audioNotificationValue": "beep", 
               "desktopNotificationDuration": "2", 
               "audioNotifications": "all", 
               "unreadAlert": "nothing", 
               "hideUnreadStatus": "all", 
               "mobilePushNotifications": "mentions"} }'
```

## Example Response

```json
{
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.63.0  | Added       |
