# stream-notify-room

This is a room stream.

Replace event from one in the list Events available:

* deleteMessage
* typing
* user-activity

```javascript
{
    "msg": "sub",
    "id": "unique-id",
    "name": "stream-notify-room",
    "params":[
        "room-id/event",
        false
    ]
}
```

