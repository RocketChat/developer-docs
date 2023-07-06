# Load History

Load room history. After the initial load, you can[ stream room messages](../../subscriptions/streamlivechatroom.md).

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument  | Example                                          | Required | Description                                                                             |
| --------- | ------------------------------------------------ | -------- | --------------------------------------------------------------------------------------- |
| `roomId`  | `64a1f373376181965ab77f54`                       | Required | The room id                                                                             |
| timestamp | null                                             | Required | The NEWEST message timestamp date (or null) to only retrieve messages before this time. |
| quantity  | 50                                               | Required | The quantity of results to be returned.                                                 |
| date      | <pre><code>{ "$date": 1480377601 }
</code></pre> | Required | The date of the last time the client got data for the room                              |

## Example Call

**Request of the latest 50 messages**

```javascript
{
    "msg": "method",
    "method": "loadHistory",
    "id": "42",
    "params": [ "room-id", null, 50, { "$date": 1480377601 } ]
}
```

**Request of the latest 50 messages, using pagination**

```javascript
{
    "msg": "method",
    "method": "loadHistory",
    "id": "42",
    "params": [ "room-id", { "$date": 1480377205 }, 50, { "$date": 1480377601 } ]
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
            ... // messages
        ],
        "unreadNotLoaded": 0
    }
}
```
