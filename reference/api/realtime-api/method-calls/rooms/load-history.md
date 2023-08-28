# Load History

Load room history. After the initial load, you can[ stream room messages](../../subscriptions/streamlivechatroom.md).

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument  | Example                                          | Required | Description                                                                             |
| --------- | ------------------------------------------------ | -------- | --------------------------------------------------------------------------------------- |
| `roomId`  | `64a1f373376181965ab77f54`                       | Required | The room id                                                                             |
| timestamp | `null`                                           | Required | The NEWEST message timestamp date (or null) to only retrieve messages before this time. |
| quantity  | 50                                               | Required | The quantity of results to be returned.                                                 |
| date      | <pre><code>{ "$date": 1480377601 }
</code></pre> | Required | The date of the last time the client got data for the room                              |

## Example Call

**Request of the latest 50 messages**

```json
{
    "msg": "method",
    "method": "loadHistory",
    "id": "42",
    "params": [ "64e37db1fedadc25c854843d", { "$date": 1480377205 }, 50, { "$date": 1480377601 } ]
}
```

**Request of the latest 50 messages, using pagination**

```javascript
{
    "msg": "method",
    "method": "loadHistory",
    "id": "42",
    "params": [ "64e37db1fedadc25c854843d", { "$date": 1480377205 }, 50, { "$date": 1480377601 } ]
}
```

## **Example Response**

The response consists of the `message`  and  `unreadNotLoaded`. The `unreadNotLoaded` counts the number of unread messages not loaded by the call.

```javascript
{
    "msg": "result",
    "id": "42",
    "result": {
        "messages": [
            {
                "_id": "PbqaTCegrjT2aMY5B",
                "rid": "64e37db1fedadc25c854843d",
                "msg": "hi",
                "ts": {
                    "$date": 1693045291715
                },
                "u": {
                    "_id": "4SebuZCHhQKvTt23o",
                    "username": "funke.olasupo",
                    "name": "Funke Olasupo"
                },
                "_updatedAt": {
                    "$date": 1693045291977
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
                                "value": "hi"
                            }
                        ]
                    }
                ]
            },
            {
                "_id": "Sj2genTaum82B4xRh",
                "rid": "64e37db1fedadc25c854843d",
                "msg": "hi",
                "ts": {
                    "$date": 1692630610658
                },
                "u": {
                    "_id": "4SebuZCHhQKvTt23o",
                    "username": "funke.olasupo",
                    "name": "Funke Olasupo"
                },
                "_updatedAt": {
                    "$date": 1692630610822
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
                                "value": "hi"
                            }
                        ]
                    }
                ]
            }
        ],
        "unreadNotLoaded": 0
    }
}

```
