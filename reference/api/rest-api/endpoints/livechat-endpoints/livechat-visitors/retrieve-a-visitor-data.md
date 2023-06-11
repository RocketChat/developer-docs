# Retrieve a visitor data

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/visitor/:token` | `no`          | `GET`       |

## Payload

| Argument | Example             | Required | Description          |
| -------- | ------------------- | -------- | -------------------- |
| `token`  | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitor/iNKE8a6k6cjbqWhWd
```

## Example Result

```javascript
{
  "visitor": {
    "_id": "sGtcfEYz852uguxaS",
    "username": "guest-7",
    "_updatedAt": "2018-09-21T14:10:56.529Z",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": [
      {
        "phoneNumber": "55 51 5555-5555"
      }
    ],
    "visitorEmails": [
      {
        "address": "visitor@rocket.chat"
      }
    ],
    "name": "Livechat Visitor",
    "livechatData": {
      "address": "Rocket.Chat street"
    }
  },
  "success": true
}
```
