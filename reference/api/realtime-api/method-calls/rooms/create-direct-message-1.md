# Create Private Group

Create a [private group](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/channels#private-channels).

| Name               | Requires Auth | Permission | Setting |
| ------------------ | ------------- | ---------- | ------- |
| createPrivateGroup | Yes           | `create-p` | `None`  |

## Payload Parameters

| Argument       | Example                                        | Required | Description                                                               |
| -------------- | ---------------------------------------------- | -------- | ------------------------------------------------------------------------- |
| `name`         | `testrc`                                       | Required | The name of the channel/group.                                            |
| `members`      | <p></p><pre><code>["test.queue"]
</code></pre> | Optional | An array containing the usernames of users to be included in the channel. |
| `readonly`     | `true`                                         | Optional | A Boolean to indicate if the room is read-only or not.                    |
| `customFields` |                                                | Optional | Custom fields for the channel.                                            |
| `extraData`    |                                                | Optional | Any extra data to associate with the channel.                             |

## Example Call

```javascript
{
    "msg": "method",
    "method": "createPrivateGroup",
    "id": "44728",
    "params": [
	"testrc7",
	["test.queue"],
	true
]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "44728",
    "result": {
        "rid": "64e543ff5fb08444f3a71f94",
        "inserted": true,
        "_id": "64e543ff5fb08444f3a71f94",
        "_updatedAt": {
            "$date": 1692746751431
        },
        "fname": "testrc7",
        "customFields": {},
        "name": "testrc7",
        "t": "p",
        "msgs": 0,
        "usersCount": 0,
        "u": {
            "_id": "4SebuZCHhQKvTt23o",
            "username": "funke.olasupo",
            "name": "Funke Olasupo"
        },
        "ts": {
            "$date": 1692746751431
        },
        "ro": true,
        "default": false,
        "sysMes": true
    }
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.38.0  | Added       |
