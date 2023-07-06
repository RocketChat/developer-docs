# Unpin Message

[Unpin ](https://docs.rocket.chat/use-rocket.chat/user-guides/messages/message-actions#pin-messages)a message.

| Name           | Requires Auth | Permission | Setting                                          |
| -------------- | ------------- | ---------- | ------------------------------------------------ |
| `unpinMessage` | Yes           |            | `Message_AllowPinning` - "Allow Message Pinning" |

## Payload Parameters

| Argument        | Example                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Required | Description         |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------- |
| `messageObject` | <pre><code>{
        "_id": "298gMs93982Le9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Whats 4*!",
        "ts": {
            "$date": 1688618709566
        },
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "_updatedAt": {
            "$date": 1688618709891
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
                        "value": "Whats 4*!"
                    }
                ]
            }
        ]
    }
</code></pre> | Required | The message object. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "unpinMessage",
    "id": "109",
    "params": [ {
        "_id": "298gMs93982Le9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Whats 4*!",
        "ts": {
            "$date": 1688618709566
        },
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "_updatedAt": {
            "$date": 1688618709891
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
                        "value": "Whats 4*!"
                    }
                ]
            }
        ]
    } ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "109",
    "result": true
}
```
