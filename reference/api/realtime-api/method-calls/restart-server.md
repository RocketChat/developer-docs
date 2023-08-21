# Restart Server

Restart your workspace server.

| Name             | Requires Auth | Permission     | Setting |
| ---------------- | ------------- | -------------- | ------- |
| `restart_server` | Yes           | restart-server | `None`  |

## Example call

```javascript
{
    "msg": "method",
    "method": "restart_server",
    "id": "1157",
    "params": []

}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "1157",
    "result": {
        "message": "The_server_will_restart_in_s_seconds",
        "params": [
            2
        ]
    }
}
```
