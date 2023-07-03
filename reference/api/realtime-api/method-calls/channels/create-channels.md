# Create Channels

Create a public channel.

| Name            | Requires Auth | Permission | Setting |
| --------------- | ------------- | ---------- | ------- |
| `createChannel` | Yes           | `create-c` |         |

## Payload Parameters

| Argument   | Example          | Required                                        | Description                                                                                                                                                                                                           |
| ---------- | ---------------- | ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`     | `channelname`    | Required                                        | The name of the channel.                                                                                                                                                                                              |
| `members`  | `["rocket.cat"]` | <p>Optional;<br> Default: <code>[]</code></p>   | <p>An array of usernames, represented as strings, for the users designated to be included in the channel.<br>If the array is empty, only the user making the request to this method will be added to the channel.</p> |
| `readOnly` | `true`           | <p>Optional;<br>Default: <code>false</code></p> | Set if the channel is read only or not. The value must be boolean.                                                                                                                                                    |



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
