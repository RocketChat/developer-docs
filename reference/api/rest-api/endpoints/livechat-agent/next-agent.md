---
description: Retrieves the data of agent available next for an incoming conversation.
---

# Next Agent

| URL                                  | Requires Auth | HTTP Method |
| ------------------------------------ | ------------- | ----------- |
| `/api/v1/livechat/agent.next/:token` | `no`          | `GET`       |

## Payload

| Argument | Example             | Required | Description          |
| -------- | ------------------- | -------- | -------------------- |
| `token`  | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/agent.next/iNKE8a6k6cjbqWhWd
```

## Example Result

```javascript
{
  "agent": {
    "_id": "7Gm3PoFCJWTCJ68XR",
    "emails": [
      {
        "address": "agent@rocket.chat",
        "verified": true
      }
    ],
    "name": "Livechat Agent",
    "username": "livechat.agent"
  },
  "success": true
}
```
