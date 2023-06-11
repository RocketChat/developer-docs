---
description: Removes a Livechat message
---

# Remove a Livechat message

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/message/:_id` | `no`          | `DELETE`    |

## Payload

| Argument | Example             | Required | Descriptio     |
| -------- | ------------------- | -------- | -------------- |
| `_id`    | `ZKWP8LfGnRHQ3ozWa` | Required | Message `_id`. |

## Example Call

```bash
curl -X DELETE \
     http://localhost:3000/api/v1/livechat/message/ZKWP8LfGnRHQ3ozWa
```

## Example Result

```javascript
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "ls": "2018-09-14T13:31:33.279Z"
  },
  "success": true
}
```

##
