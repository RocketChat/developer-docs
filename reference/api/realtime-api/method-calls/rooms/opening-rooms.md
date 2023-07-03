# Opening Rooms

When a room is opened, it becomes visible in the channel list on the sidebar, and the "open" property in the user's subscription for that room is set to `true`.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>openRoom</code></td><td>Yes</td><td></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id |

## Example Call

```javascript
{
    "msg": "method",
    "method": "openRoom",
    "id": "19",
    "params": [
        "64a1f540376181965ab77f5b"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "19",
    "result": 1
}
```
