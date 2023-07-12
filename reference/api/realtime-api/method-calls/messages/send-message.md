# Send Message

Send a message to a [room](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms).

| Name          | Requires Auth | Permission | Setting |
| ------------- | ------------- | ---------- | ------- |
| `sendMessage` | Yes           |            |         |

## Payload Parameters

| Argument  | Example                                                                                                                                                                                                                 | Required | Description         |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------- |
| `message` | <pre class="language-json"><code class="lang-json"><strong> {
</strong>            "_id": "8gMsLe9ApZjo2D2iB",
            "rid": "64a1f373376181965ab77f54",
            "msg": "Hello World!"
        }
</code></pre> | Required | The message object. |

The `message` object contains the following properties:

<table data-header-hidden><thead><tr><th></th><th width="201"></th><th></th></tr></thead><tbody><tr><td><code>_id</code></td><td><code>8gMsLe9ApZjo2D2iB</code></td><td>The message id</td></tr><tr><td><code>rid</code></td><td><code>64a1f373376181965ab77f54</code></td><td>The room id where the message should be sent</td></tr><tr><td><code>msg</code></td><td><code>Hello World</code></td><td>The message content to be sent.</td></tr></tbody></table>

## Example Call

```javascript
{
    "msg": "method",
    "method": "sendMessage",
    "id": "423",
    "params": [
        {
            "_id": "8gMsLe9A7pZjo2D2iB",
            "rid": "64a1f373376181965ab77f54",
            "msg": "Hello World!"
        }
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "423",
    "result": {
        "_id": "8gMsLe9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Hello World!",
        "ts": {
            "$date": 1688421337724
        },
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "_updatedAt": {
            "$date": 1688421337830
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
        ]
    }
}
```

{% hint style="info" %}
To send a file, use the [Upload File to a Room](../../../rest-api/endpoints/rooms/rooms-endpoints/upload-file-to-a-room.md) endpoint.
{% endhint %}
