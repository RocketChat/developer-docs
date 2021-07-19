---
description: Retrieve the visitor info
---

# Get the visitor info

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/visitors.info` | `yes` | `GET` |

## Query Parameter

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `visitorId` | `iNKE8a6k6cjbqWhWd` | Required | The visitor's id. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitors.info?visitorId=iNKE8a6k6cjbqWhWd
```

## Example Result

```javascript
{
    "visitor": {
        "_id": "L64iXAKtGaPfusnem",
        "username": "guest-4",
        "_updatedAt": "2019-10-21T19:36:47.960Z",
        "token": "hzf48867bv9lwjzigk2tk"
    },
    "success": true
}
```

