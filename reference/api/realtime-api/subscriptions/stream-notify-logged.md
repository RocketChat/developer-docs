# stream-notify-logged

Stream for logged in users.

## Events

* Users:NameChanged
* Users:Deleted
* updateAvatar
* updateEmojiCustom
* deleteEmojiCustom
* roles-change
* [user-status](stream-notify-logged.md#user-status)

## Example Call

```javascript
{
    "msg": "sub",
    "id": "7489",
    "name": "stream-notify-logged",
    "params":[
        "user-status",
        false
    ]
}
```

## Example Response

### user-status

Event about user status changes.&#x20;

```javascript
{
    "msg": "changed",
    "collection": "stream-notify-logged",
    "id": "id",
    "fields": {
        "eventName": "user-status",
        "args": [["uNqJeFuag2344i62k", "rocket.cat", 1]]
    }
}
```



The `args` property will always be an array with the following values:

| Argument   | Example           | Description                                                                                                                                                                       |
| ---------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `user_id`  | uNqJeFuag2344i62k | The id of the                                                                                                                                                                     |
| `username` | `rocket.cat`      | The username.                                                                                                                                                                     |
| `status`   | `1`               | <p>The indicator of the user status. The integers represent the following: <br>0 - <code>offline</code>, 1-<code>online</code>, 2 - <code>away</code>, 3 - <code>busy</code>.</p> |

*
