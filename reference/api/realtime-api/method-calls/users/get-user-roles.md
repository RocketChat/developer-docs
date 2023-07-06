# Get User Roles

Get the role(s) of a user in a room. It can be used to identify key users in the workspace.

| Name           | Requires Auth | Permission | Setting |
| -------------- | ------------- | ---------- | ------- |
| `getUserRoles` | Yes           |            |         |

## Example Call

```javascript
{
    "msg": "method",
    "method": "listEmojiCustom",
    "id": "42",
    "params": []
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "4022",
    "result": [
        {
            "_id": "LFdhbcNHx5zsMA7T4",
            "roles": [
                "admin"
            ],
            "username": "test.rc"
        }
    ]
}
```
