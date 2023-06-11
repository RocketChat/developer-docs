# Create Call Center Visitor

| **URL**                   | **Requires Authentication** | **HTTP Method** |
| ------------------------- | --------------------------- | --------------- |
| `api/v1/livechat/visitor` | Yes                         | POST            |

### Payload

```json
{
  "visitor": {
    "token": "867ad6a09fc4af29f6f1f2a9cf1deaba"
  }
}
```

### Example Call

```json
curl --location --request POST 'localhost:3000/api/v1/livechat/visitor' \
--header 'Content-Type: application/json' \
--data-raw '{
    "visitor": {
        "token": "867ad6a09fc4af29f6f1f2a9cf1deaba"
    }
}'
```

### Example Response



```json
{
    "visitor": {
        "_id": "b3c7SMriL729R3J8w",
        "username": "guest-2",
        "status": "online",
        "ts": "2022-06-29T06:05:01.392Z",
        "_updatedAt": "2022-06-29T06:05:01.408Z",
        "token": "867ad6a09fc4af29f6f1f2a9cf1deaba"
    },
    "success": true
}
```
