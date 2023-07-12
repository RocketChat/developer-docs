---
description: Get info about an agent or manager
---

# Get info of an agent or manager

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/users/:type/:_id` | `yes`         | `GET`       |

## Payload

| Argument | Example             | Required | Description                         |
| -------- | ------------------- | -------- | ----------------------------------- |
| `type`   | `agent`             | Required | Can be either `agent` or `manager`. |
| `_id`    | `SQafHvoFPuB57NmBD` | Required | The user `_id`.                     |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/users/agent/SQafHvoFPuB57NmBD
```

## Example Result

```javascript
{
  "user": {
    "_id": "SQafHvoFPuB57NmBD",
    "username": "john.doe"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.42.0  | Added       |

##
