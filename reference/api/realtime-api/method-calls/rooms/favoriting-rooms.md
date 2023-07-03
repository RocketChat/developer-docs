# Favorite/Unfavourite a Room

Favorite or unfavorite room.

<table><thead><tr><th width="204">Name</th><th>Requires Auth</th><th>Permission</th><th>Setting</th></tr></thead><tbody><tr><td><code>toggleFavorite</code></td><td>Yes</td><td></td><td></td></tr></tbody></table>

## Payload Parameters

| Argument   | Example                    | Required                                          | Description                                                                                |
| ---------- | -------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `roomId`   | `64a1f373376181965ab77f54` | Required                                          | The room id                                                                                |
| `favorite` | `false`                    | <p>Optional:</p><p>Default: <code>true</code></p> | <p><code>true</code> - Mark as favorite.<br><code>false</code> - Remove from favorite.</p> |

## Example Call

```javascript
{
    "msg": "method",
    "method": "toggleFavorite",
    "id": "16",
    "params": [
        "64a1f540376181965ab77f5b",
        false
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "16",
    "result": 1
}
```

