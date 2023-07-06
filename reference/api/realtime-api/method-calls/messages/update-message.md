# Update Message

Update a message.

| Name            | Requires Auth | Permission     | Setting                                          |
| --------------- | ------------- | -------------- | ------------------------------------------------ |
| `updateMessage` | Yes           | `edit-message` | `Message_AllowEditing` - "Allow Message Editing" |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument            | Example                                                                                                                                        | Required | Description                                                                                   |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------- |
| `textMessageObject` | <pre><code>{
        "_id": "298gMs93982Le9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Whats 4*!"
}
</code></pre> | Required | The [Message Object](../../../schema-definition/message.md) containing only the updated `msg` |

## Settings

There are two essential settings to consider when deleting messages.

### Message\_AllowEditing

It is represented as a boolean (true/false), which determines whether message editing is permitted.

### Message\_AllowDeleting\_BlockDeleteInMinutes

It is represented as an integer and offers more control over the edit functionality. When set to `0`, editing is allowed without any time restrictions. However, if the value is greater than `0`, there is a time-based restriction where editing is blocked/disabled after the specified duration has passed.

## Example Call

```javascript
{
    "msg": "method",
    "method": "updateMessage",
    "id": "42",
    "params": [{
        "_id": "298gMs93982Le9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Whats 4*!"
}]
        
}

```

## Example Response

```javascript
{
    "msg": "result",
    "id": "42"
}
```
