# Delete Message

<figure><img src="../../../../../.gitbook/assets/Deprecated.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This method is planned to be removed by 7.0.0. Use the [`/chat.delete`](https://developer.rocket.chat/reference/api/rest-api/endpoints/messaging/chat-endpoints/delete) endpoint instead.
{% endhint %}

Delete a message by the message id.

<table><thead><tr><th>Name</th><th width="150">Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>deleteMessage</code></td><td>Yes</td><td><code>delete-message</code></td><td><code>Message_AllowDeleting</code> - "Allow Message Deleting"</td></tr></tbody></table>

## Settings

There are two essential settings to consider when deleting messages.

### Message\_AllowDeleting

It is represented as a boolean (true/false), which determines whether message deletion is permitted.

### Message\_AllowDeleting\_BlockDeleteInMinutes

It is represented as an integer and offers more granular control over the deletion functionality. When set to `0`, deletion is allowed without any time restrictions. However, if the value is greater than `0`, there is a time-based restriction where deletion is blocked/disabled after the specified duration has passed.

{% hint style="info" %}
Users with the `delete-message` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions) can delete any message, while still adhering to the rules set by the `Message_AllowDeleting_BlockDeleteInMinutes` setting.

Alternatively, users with the `force-delete-message`  [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions) can delete any message without adhering to  the rules set by the`Message_AllowDeleting_BlockDeleteInMinutes` setting.
{% endhint %}

## Payload Parameters

| Argument     | Example                    | Required | Description |
| ------------ | -------------------------- | -------- | ----------- |
| `message_id` | `64a1f373376181965ab77f54` | Required | The room id |

## Example Call

```javascript
{
    "msg": "method",
    "method": "deleteMessage",
    "id": "42",
    "params": [ 
		{ "_id": "8gMsLe9ApZjo2D2iB"} 
	]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "42"
}
```
