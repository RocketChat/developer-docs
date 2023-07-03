# Method Calls

Method calls are used to perform actions based on given data. The response to these calls is asynchronous, meaning they don't occur in a specific order. To track the outcome of a call, it's essential to use a unique ID. This ID will be used in the response, allowing the client to identify and retrieve the result of the corresponding call.

Here is an example of a method call and response for [creating a channel](channels/create-channels.md):

## Example Call

```javascript
{
    "msg": "method",
    "method": "createChannel",
    "id": "2",
    "params": [
        "test-websocket",
        ["funke.olasupo"],
        false
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "2",
    "result": [
        { "rid": "BBkfgYT2azf7RPTTg" }
    ]
}
```

{% hint style="info" %}
The id is the only way to recognize which method call a response belongs to.
{% endhint %}
