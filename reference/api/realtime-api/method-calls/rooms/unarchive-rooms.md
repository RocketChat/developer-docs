# Unarchive Rooms

Unarchiving a room reverses its read-only status and returns it to the channel list on the left sidebar.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>unarchiveRoom</code></td><td>Yes</td><td><code>unarchive-room</code></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument | Example                    | Required | Description  |
| -------- | -------------------------- | -------- | ------------ |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "unarchiveRoom",
    "id": "5",
    "params": [
        "64a1f540376181965ab77f5b"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "5"
}
```
