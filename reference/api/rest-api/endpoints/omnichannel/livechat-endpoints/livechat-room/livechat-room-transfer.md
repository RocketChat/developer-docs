---
description: Transfer an omnichannel conversation
---

# Livechat Room Transfer

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/room.transfer` | `no`          | `POST`      |

## Payload

| Argument     | Example             | Required | Description           |
| ------------ | ------------------- | -------- | --------------------- |
| `rid`        | `XFzMqgn33DcsQkpJp` | Required | The room `_id`.       |
| `token`      | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`.  |
| `department` | `wXpPLofkffqWAwDNF` | Required | The new `department`. |

## Example payload

```javascript
{
  "rid": "XFzMqgn33DcsQkpJp",
  "token": "iNKE8a6k6cjbqWhWd",
  "department": "wXpPLofkffqWAwDNF"
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/room.transfer \
     -d '{"rid": "XFzMqgn33DcsQkpJp", "token": "iNKE8a6k6cjbqWhWd", "department": "wXpPLofkffqWAwDNF"}'
```

## Example Result

```javascript
{
  "room": {
    "_id": "XFzMqgn33DcsQkpJp",
    "servedBy": {
      "_id": "wiyTfFKXr5GhgRu9A",
      "username": "livechat.agent"
    },
    "open": true,
    "departmentId": "wXpPLofkffqWAwDNF"
  },
  "success": true
}
```
