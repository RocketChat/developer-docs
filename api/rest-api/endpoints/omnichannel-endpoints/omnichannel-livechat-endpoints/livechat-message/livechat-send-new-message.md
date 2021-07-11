---
description: Send a new Livechat message
---

# Livechat Send New Message

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/message` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | Visitor `token`. |
| `rid` | `zRAeTszXor8CCPceB` | Required | Room `_id`. |
| `msg` | `sending livechat message..` | Required | Message `text`. |
| `_id` |  | Optional | Message `_id`. |
| `agent` |  | Optional | Room `agent`. |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "rid": "zRAeTszXor8CCPceB",
  "msg": "sending livechat message.."
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/message \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "rid": "zRAeTszXor8CCPceB", "msg": "sending livechat message.."}'
```

## Example Result

```javascript
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "msg": "sending livechat message..",
    "u": {
      "_id": "iNKE8a6k6cjbqWhWd",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "ls": "2018-09-14T13:31:33.201Z"
  },
  "success": true
}
```



