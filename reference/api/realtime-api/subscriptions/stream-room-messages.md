# stream-room-messages

## Subscribe

This is the room messages stream. You just need the room ID for subscribing.

### DDP Message

```json
{
    "msg":"sub",
    "id":"6NctZomXL3ZdtKNsn",
    "name":"stream-livechat-room",
    "params":[
        "KTZqPAR9DQGxKcxzf",
        {
            "useCollection":false,
            "args":[
                {
                    "token":"jkGaw6duhiuh45"
                }
            ]
        }
    ]
};
```

### Sample Response

```json
{
    "msg":"ready",
    "subs":[
        "JHalkajwdh67"
    ]
j
```

## &#x20;Unsubscribe

To unsubscribe from a room, send "unsub", along with the ID of the previous subscribe message.

```javascript
{
    "msg": "unsub",
    "id": "unique-id",
}
```

If you want to subscribe to a user's messages stream, just pass `__my_messages__` as the room ID.
