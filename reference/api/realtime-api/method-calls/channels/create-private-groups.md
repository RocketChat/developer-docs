# Create Private Groups

Creates a [private channel](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/channels#private-channels).

| Name            | Requires Auth | Permission | Setting |
| --------------- | ------------- | ---------- | ------- |
| `createChannel` | Yes           | `create-p` |         |

## Payload Parameters

| Argument  | Example       | Required                                      | Description                                                                                                                                                                                                           |
| --------- | ------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`    | `channelname` | Required                                      | The name of the channel.                                                                                                                                                                                              |
| `members` | `["test.rc"]` | <p>Optional;<br> Default: <code>[]</code></p> | <p>An array of usernames, represented as strings, for the users designated to be included in the channel.<br>If the array is empty, only the user making the request to this method will be added to the channel.</p> |

## Example Call

```javascript
{
    "msg": "method",
    "method": "createPrivateGroup",
    "id": "8d89",
    "params": [
         "test-private-websockset",
        ["rocket.cat"]
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "8d89",
    "result": {
        "rid": "64a37803730ef04d3db2556f",
        "inserted": true,
        "fname": "test-private-websockset",
        "_updatedAt": {
            "$date": 1688434691876
        },
        "customFields": {},
        "name": "test-privadte-websockset",
        "t": "p",
        "msgs": 0,
        "usersCount": 0,
        "u": {
            "_id": "LFdhbcNHx5zsMA7T4",
            "username": "test.rc",
            "name": "Test RC"
        },
        "ts": {
            "$date": 1688434691876
        },
        "ro": false,
        "default": false,
        "sysMes": true,
        "_id": "64a37803730ef04d3db2556f"
    }
}
```
