# Check Username Availability

Confirm if a username is available.

| Name                        | Requires Auth | Permission | Setting |
| --------------------------- | ------------- | ---------- | ------- |
| `checkUsernameAvailability` | Yes           |            | `None`  |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument   | Example     | Required | Description                        |
| ---------- | ----------- | -------- | ---------------------------------- |
| `username` | `john.wood` | Required | The username you are checking for. |

## Example call

```javascript
{
    "msg": "method",
    "method": "checkUsernameAvailability",
    "id": "117",
    "params": [
        "funke"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "117",
    "result": true
}
```
