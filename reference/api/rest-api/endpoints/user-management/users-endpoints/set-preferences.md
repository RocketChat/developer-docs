# Set Preferences

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.setPreferences</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
If you want to edit another user's preferences, you need the permission `edit-other-user-info`_._
{% endhint %}

## Body Parameters

<table><thead><tr><th width="229.33333333333331">Key</th><th width="202">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code></td><td><code>BsNr28znDkG8ae</code></td><td>The user ID whose preferences you want to change. <br>If an ID is not provided, the preferences will be set for the user who is sending the request.</td></tr><tr><td><code>data</code><mark style="color:red;"><code>*</code></mark></td><td><code>"data": { ... }</code></td><td>The object with the following preference details.</td></tr><tr><td><code>language</code></td><td><code>en</code></td><td>The preferred language for the user.</td></tr><tr><td><code>newRoomNotification</code></td><td><code>door</code></td><td>New room notification sound.</td></tr><tr><td><code>newMessageNotification</code></td><td><code>chime</code></td><td>New message notification sound.</td></tr><tr><td><code>muteFocusedConversations</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to mute focused conversations.</td></tr><tr><td><code>clockMode</code></td><td><code>1</code></td><td><p>The valid display formats for the clock. You can enter the values <code>0</code>, <code>1</code>, or <code>2</code>.</p><ul><li><code>0</code>: System default</li><li><code>1</code>: 12-hour clock</li><li><code>2</code>: 24-hour clock</li></ul></td></tr><tr><td><code>useEmojis</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to use emojis.</td></tr><tr><td><code>convertAsciiEmoji</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to convert ASCII emojis.</td></tr><tr><td><code>saveMobileBandwidth</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to save mobile bandwidth.</td></tr><tr><td><code>collapseMediaByDefault</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to collapse media by default.</td></tr><tr><td><code>autoImageLoad</code></td><td><code>true</code></td><td>A boolean value indicates whether the user has enabled the option to load images automatically.</td></tr><tr><td><code>emailNotificationMode</code></td><td><code>mentions</code></td><td>The preferred mode for email notifications.</td></tr><tr><td><code>unreadAlert</code></td><td><code>true</code></td><td>A boolean value indicates whether the user has enabled the option.</td></tr><tr><td><code>notificationsSoundVolume</code></td><td><code>100</code></td><td>The sound volume for notifications.</td></tr><tr><td><code>desktopNotifications</code></td><td><code>mentions</code></td><td><p>The type of desktop notifications.</p><ul><li><code>all</code>: Get desktop notifications for all messages.</li><li><code>mentions</code>: Get the notifications only for mentions.</li><li><code>nothing</code>: Get no desktop notifications.</li></ul></td></tr><tr><td><code>pushNotifications</code></td><td><code>mentions</code></td><td><p>The mobile push notification.</p><ul><li><code>all</code>: Get mobile notifications for all messages.</li><li><code>mentions</code>: Get the notifications only for mentions.</li><li><code>nothing</code>: Get no mobile notifications</li></ul></td></tr><tr><td><code>enableAutoAway</code></td><td><code>false</code></td><td>A boolean value that indicates whether the user has enabled the option to update the status as away after a certain amount of idle time.</td></tr><tr><td><code>highlights</code></td><td><code>["deploy", "docker"]</code></td><td>The message highlights section. You will be notified when someone mentions a word or phrase that you add here. Highlight words are not case-sensitive.</td></tr><tr><td><code>messageViewMode</code></td><td><code>1</code></td><td><p>The preferred view mode for the messages. The available options are:</p><ul><li><code>0</code> - Normal</li><li><code>1</code> - Cozy</li><li><code>2</code> - Compact</li></ul></td></tr><tr><td><code>hideUsernames</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to hide usernames.</td></tr><tr><td><code>hideRoles</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to hide roles.</td></tr><tr><td><code>displayAvatars</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to display user avatars.</td></tr><tr><td><code>hideFlexTab</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option.</td></tr><tr><td><code>sendOnEnter</code></td><td><code>normal</code></td><td><p>Set how you want the <strong>Enter</strong> key to behave when sending messages.</p><ul><li><code>normal</code> - Send messages with the <strong>Enter</strong> key.</li><li><code>alternative</code> - Send messages with <strong>Enter</strong> + <strong>Ctrl/Alt/Shift/Cmd</strong>.</li><li><code>desktop</code> - Send messages with <strong>Enter</strong> only on the desktop.</li></ul></td></tr><tr><td><code>idleTimeLimit</code></td><td><code>300</code></td><td>The time limit that is to be considered as idle time.</td></tr><tr><td><code>sidebarShowFavorites</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to show favorites on the sidebar.</td></tr><tr><td><code>sidebarShowUnread</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to show unread messages in the sidebar.</td></tr><tr><td><code>sidebarSortby</code></td><td><code>activity</code></td><td><p>To sort the messages in the sidebar alphabetically or by activity. The values can be:</p><ul><li><code>activity</code></li><li><code>alphabetical</code> </li></ul></td></tr><tr><td><code>sidebarViewMode</code></td><td><code>condensed</code></td><td><p>The view mode of the sidebar. The values can be:</p><ul><li><code>extended</code></li><li><code>medium</code></li><li><code>condensed</code> </li></ul></td></tr><tr><td><code>sidebarDisplayAvatar</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to display avatars in the sidebar.</td></tr><tr><td><code>sidebarGroupByType</code></td><td><code>true</code></td><td>A boolean value that indicates whether the user has enabled the option to show the grouped values in the sidebar.</td></tr><tr><td><code>dontAskAgainList</code></td><td><code>"dontAskAgainList":[{"action":"hideRoom","label":"Hide"}]</code></td><td>This field stores all the "warnings" a user opted not to be displayed again. An example where this works is when hiding a room.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.setPreferences \
     -d '{ "userId": "BsNr28znDkG8aeo7W", "data": { } }'
```

## Example Result

```json
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
