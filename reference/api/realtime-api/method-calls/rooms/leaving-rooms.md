# Leaving Rooms

You can leave any room except for direct messages, and you cannot leave rooms where you are the last owner.\


<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>leaveRoom</code></td><td>Yes</td><td></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id |

## Example Call

```javascript
{
    "msg": "method",
    "method": "leaveRoom",
    "id": "11",
    "params": [
        "64a1f540376181965ab77f5b"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "11"
}
```
