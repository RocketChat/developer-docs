# Delete Rooms

Delete a public or private room.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th width="150">Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>eraseRoom</code></td><td>Yes</td><td><code>delete-c</code> <em>or</em> <code>delete-p</code></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id |



## Example Call

```javascript
{
    "msg": "method",
    "method": "eraseRoom",
    "id": "92",
    "params": [
        "64a1f540376181965ab77f5b"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "92",
    "result": true
}
```
