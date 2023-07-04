# Set/Unset Reactions

[Reacting to messages](https://docs.rocket.chat/use-rocket.chat/user-guides/messages/message-actions#reactions) provides a convenient means of expressing reactions through emojis, offering various options for integrations, inquiries, and other creative purposes.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>setReaction</code></td><td>Yes</td><td></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument      | Example             | Required | Description                                                                                                                                                                                       |
| ------------- | ------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `emoji`       | `:nerd:`            | Required | The emoji.                                                                                                                                                                                        |
| `message_id`  | `8gMsLe9ApZjo2D2iB` | Required | The id of the message you want to react to.                                                                                                                                                       |
| `setReaction` | `true`              | Required | <p>It can only be <code>true</code> or <code>false</code>.<br><code>true</code>: - Set the emoji reaction  to the message.<br><code>false</code>: Remove the emoji reaction from the message.</p> |

## Example Call

```javascript
{
    "msg": "method",
    "method": "setReaction",
    "id": "22",
    "params": [
        ":nerd:",
        "8gMsLe9ApZjo2D2iB",
        true
    ]
}

```

## Example Response

```javascript
{
    "msg": "result",
    "id": "22"
}
```
