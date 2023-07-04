# Star/Unstar Message

[Starring messages](https://docs.rocket.chat/use-rocket.chat/user-guides/messages/message-actions#star-messages) enables users to save them easily for future reference or personal use.

| Name          | Requires Auth | Permission | Setting                                            |
| ------------- | ------------- | ---------- | -------------------------------------------------- |
| `starMessage` | Yes           |            | `Message_AllowStarring` - "Allow Message Starring" |

## Payload Parameters

| Argument  | Example                                                                                                                                                                         | Required | Description         |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------- |
| `message` | <pre class="language-json"><code class="lang-json">{
        "_id": "8gMsLe9ApZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "starred": true
    }
</code></pre> | Required | The message object. |

The `message` object contains the following properties:

<table data-header-hidden><thead><tr><th></th><th width="201"></th><th></th><th></th></tr></thead><tbody><tr><td><code>_id</code></td><td><code>8gMsLe9ApZjo2D2iB</code></td><td>Required</td><td>The message id</td></tr><tr><td><code>rid</code></td><td><code>64a1f373376181965ab77f54</code></td><td>Required</td><td>The room id where the message should be sent</td></tr><tr><td><code>starred</code></td><td><code>true</code></td><td>Required</td><td>It can only be <code>true</code> or <code>false</code>.<br><code>true</code>: - Star the message.<br><code>false</code>: Unstar the  message.</td></tr></tbody></table>

## Example Call

```javascript
{
    "msg": "method",
    "method": "starMessage",
    "id": "21",
    "params": [{
        "_id": "8gMsLe9ApZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "starred": true
    }]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "21",
    "result": true
}
```
