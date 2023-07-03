# Hiding Rooms

When a room is hidden, it no longer appears in the channel list, and the "open" property is set to `false` in the user's subscription for that room.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>hideRoom</code></td><td>Yes</td><td></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id |

## Example Call

```javascript
{
    "msg": "method",
    "method": "hideRoom",
    "id": "14",
    "params": [
        "64a1f540376181965ab77f5b"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "14",
    "result": 1
}
```
