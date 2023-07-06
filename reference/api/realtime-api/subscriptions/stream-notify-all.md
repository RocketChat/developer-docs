# stream-notify-all

General user-wide stream.

## Available Events

* roles-change
* updateEmojiCustom
* deleteEmojiCustom
* updateAvatar
* public-settings-changed
* permissions-changed

## Example Call

```javascript
{
    "msg": "sub",
    "id": "unique-id",
    "name": "stream-notify-all",
    "params":[
        "event",
        false
    ]
}
```

## Example Response

```
{
    "msg": "ready",
    "subs": [
        "03903"
    ]
}
```
