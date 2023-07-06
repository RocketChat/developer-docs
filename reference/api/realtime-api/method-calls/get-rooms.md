# Get Rooms

Get all rooms a user belongs to.

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                                          | Required | Description                                                                                                                                            |
| -------- | ------------------------------------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `date`   | <pre><code>{ "$date": 1480377601 }
</code></pre> | Required | A timestamp with the latest client update time in order to just send what changed since last call. If it's the first time calling, send a `0` as date. |

## Example call

```javascript
{
    "msg": "method",
    "method": "rooms/get",
    "id": "42",
    "params": [ { "$date": 1480377601 } ]
}
```

## Example Response

The `result` is an object with two fields: `update` and `remove`.

### Remove field

The `remove` field is a collection of room id identifying the rooms that were removed from the server.

### Update field

The `update` field is a collection of [`room`](../../schema-definition/room.md) and its content varies according to the `room type`.&#x20;

```javascript
{
    "msg": "result",
    "id": "42",
    "result": {
        "update": [
            ... // rooms
        ],
        "remove": [
            ... // room ids
        ]
    }
}
```
