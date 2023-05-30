---
description: Retrieve livechat messages history (all messages in a conversation)
---

# Load Livechat messages history

| URL                                      | Requires Auth | HTTP Method |
| ---------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/messages.history/:rid` | `no`          | `GET`       |

## Payload

| Argument | Example             | Required | Description     |
| -------- | ------------------- | -------- | --------------- |
| `rid`    | `KuACMJ5MpN6SfAFWg` | Required | The room `_id`. |

## Query Parameters

| Argument | Example             | Required | Description                     |
| -------- | ------------------- | -------- | ------------------------------- |
| `token`  | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`.            |
| `ls`     |                     | Optional | The timestamp to start loading. |
| `end`    |                     | Optional | The timestamp limit to load.    |
| `limit`  |                     | Optional | The number of messages to load. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/messages.history/KuACMJ5MpN6SfAFWg?token=iNKE8a6k6cjbqWhWd
```

## Example Result

```javascript
{
  "messages": [{
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "rid": "KuACMJ5MpN6SfAFWg",
    "msg": "editing livechat message..",
    "token": "iNKE8a6k6cjbqWhWd",
    "alias": "Livechat Visitor",
    "ls": "2018-09-14T13:31:33.201Z",
    "u": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "mentions": [],
    "channels": [],
    "_updatedAt": "2018-09-14T13:31:33.222Z",
    "editedAt": "2018-09-14T13:31:33.219Z",
    "editedBy": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4"
    },
    "urls": []
  }],
  "unreadNotLoaded": 0,
  "success": true
}
```
