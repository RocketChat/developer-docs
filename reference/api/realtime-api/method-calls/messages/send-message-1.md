# Get Single Message

Get a single message by the message id.

| Name               | Requires Auth | Permission | Setting |
| ------------------ | ------------- | ---------- | ------- |
| `getSingleMessage` | Yes           |            |         |

## Payload Parameters

| Argument     | Example             | Required | Description     |
| ------------ | ------------------- | -------- | --------------- |
| `message_id` | `8gMsLe9ApZjo2D2iB` | Required | The message id. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "getSingleMessage",
    "id": "23",
    "params": [
        "8gMsLe9ApZjo2D2iB"
      
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "23",
    "result": {
        "_id": "8gMsLe9ApZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Hello World!",
        "ts": {
            "$date": 1688421173424
        },
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "_updatedAt": {
            "$date": 1688421428832
        },
        "urls": [],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "Hello World!"
                    }
                ]
            }
        ],
        "starred": []
    }
}
```
