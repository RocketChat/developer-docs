# Subscriptions

Streams are a way of plugging into a continuous source of updates (changes). Any subscriber registered will receive the latest changes as they occur.&#x20;

## Subscribe to a Stream

To subscribe to a stream, you must send a message with msg: sub, a unique id, the stream name, and the parameters to be applied on the stream.

```javascript
{
    "msg": "sub",
    "id": "unique-id",
    "name": "the-stream",
    "params":[ "event", false ]
}
```

{% hint style="info" %}
You must be logged in before you send any subscription request.
{% endhint %}

Recent changes to the stream API aim to notify subscribers about changes more selectively, which could cause issues with existing drivers. To ensure compatibility, a boolean parameter is suggested as the last option. If set to `true`, subscribers will receive an "add" event whenever something new is created. This parameter allows subscribers to decide if they need to be notified about all changes or only specific ones, keeping things compatible with older drivers.

## Unsubscribe from a Stream

To unsubscribe from a room, send this request:

```javascript
{
    "msg": "unsub",
    "id": "subscription-id"
}
```

The response will look like this:

```javascript
{
    "msg": "nosub",
    "id": "subscription-id"
}
```

When you make a call to an invalid or non-existent `subscription_id`, the response will not produce an error. Instead, it will respond with at least a "msg" field set to "nosub" and include the provided `id` value. If no `id` was provided, the `id` field will be omitted from the response.&#x20;
