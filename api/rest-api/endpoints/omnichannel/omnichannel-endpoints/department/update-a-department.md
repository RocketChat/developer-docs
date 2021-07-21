---
description: Update a department
---

# Update a department

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/department/:_id` | `yes` | `PUT` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `_id` | `iTfLCX3qqwKgf5uqg` | Required | Department `_id`. |

## Example payload

```javascript
{
  "department": {
    "enabled": true,
    "showOnRegistration": true,
    "name": "new from api - live"
  },
  "agents": [{
    "agentId": "SQafHvoFPuB57NmBD",
    "username": "john.doe",
    "count": 0,
    "order": 0
  }]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X PUT \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/department/iTfLCX3qqwKgf5uqg \
    -d '{"department": {"enabled": true, "name": "new from api - live", "showOnRegistration": true}, "agents": [{"agentId": "SQafHvoFPuB57NmBD", "username": "john.doe"}] }'
```

## Example Result

```javascript
{
  "department": {
    "_id": "iTfLCX3qqwKgf5uqg",
    "enabled": true,
    "name": "new from api - live",
    "description": null,
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:30:02.643Z"
  },
  "agents": [
    {
      "_id": "DDjZbhTF74n3NBuWK",
      "agentId": "SQafHvoFPuB57NmBD",
      "departmentId": "iTfLCX3qqwKgf5uqg",
      "username": "john.doe",
      "count": 0,
      "order": 0,
      "_updatedAt": "2016-12-13T17:30:02.656Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.42.0 | Added |

## 

