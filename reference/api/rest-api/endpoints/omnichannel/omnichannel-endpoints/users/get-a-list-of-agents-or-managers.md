---
description: Get a list of agents or managers.
---

# Get a list of agents or managers

It supports the Offset, Count, and Sort Query Parameters.

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `/api/v1/livechat/users/:type` | `yes`         | `GET`       |

## Payload

| Argument | Example | Required | Description                         |
| -------- | ------- | -------- | ----------------------------------- |
| `type`   | `agent` | Required | Can be either `agent` or `manager`. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/users/agent
```

## Example Result

```javascript
{
  "users": [
    {
      "_id": "aobEdbYhXfu5hkeqG",
      "username": "john.doe"
    },
    {
      "_id": "SQafHvoFPuB57NmBD",
      "username": "doe.john"
    }
  ],
  "success": true
}
```

## Change Log

<table><thead><tr><th>Version</th><th width="376">Description</th></tr></thead><tbody><tr><td>2.2.0</td><td>Added support to pagination</td></tr><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>

##
