# Create Direct Message

Create a [direct message](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/direct-messages).

| Name                  | Requires Auth | Permission | Setting |
| --------------------- | ------------- | ---------- | ------- |
| `createDirectMessage` | Yes           |            |         |

## Payload Parameters

| Argument   | Example  | Required | Description                                      |
| ---------- | -------- | -------- | ------------------------------------------------ |
| `username` | `testrc` | Required | The usernames to be added to the direct message. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "createDirectMessage",
    "id": "472",
    "params": ["testrc"]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "472",
    "result": {
        "t": "d",
        "rid": "LFdhbcNHx5zsMA7T4ZoJM4tvohREwJbtAh",
        "usernames": [
            "test.rc",
            "testrc"
        ]
    }
}
```
