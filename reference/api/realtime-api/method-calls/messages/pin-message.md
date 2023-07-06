# Pin Message

[Pin](https://docs.rocket.chat/use-rocket.chat/user-guides/messages/message-actions#pin-messages) a message.

| Name         | Requires Auth | Permission | Setting                                          |
| ------------ | ------------- | ---------- | ------------------------------------------------ |
| `pinMessage` | Yes           |            | `Message_AllowPinning` - "Allow Message Pinning" |

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
    "method": "pinMessage",
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
    "result": {
        "_id": "64a64761605f9022b067fa3a",
        "t": "message_pinned",
        "rid": "64a1f373376181965ab77f54",
        "ts": {
            "$date": 1688618849979
        },
        "msg": "",
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "groupable": false,
        "attachments": [
            {
                "text": "Whats 4*!",
                "author_name": "test.rc",
                "author_icon": "/avatar/test.rc",
                "ts": {
                    "$date": 1688618709566
                },
                "attachments": []
            }
        ],
        "_updatedAt": {
            "$date": 1688618849989
        }
    }
}
```
