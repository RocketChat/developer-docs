---
description: Register a new agent or manager.
---

# Register new agent or manager

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `/api/v1/livechat/users/:type` | `yes`         | `POST`      |

## Payload

| Argument | Example | Required | Description                         |
| -------- | ------- | -------- | ----------------------------------- |
| `type`   | `agent` | Required | Can be either `agent` or `manager`. |

## Example payload

```javascript
{
  "username":"john.doe"
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/users/agent \
    -d '{"username":"john.doe"}'
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
