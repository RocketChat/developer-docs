# Register a new department

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/livechat/department` | `yes`         | `POST`      |

## Example payload

```json
{
  "department": {
    "enabled": false,
    "showOnRegistration": true,
    "email": "email@email.com",
    "showOnRegistration": true,
    "name": "new from api",
    "description": "created from api"
  },
  "agents": [{
    "agentId": "SQafHvoFPuB57NmBD",
    "count": 0,
    "order": 0
  }]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/department \
    -d '{"department": {"enabled": false, "showOnRegistration": true, "name": "new from api", email: "john@doe.com", showOnOfflineForm: true }, "agents": [{ "agentId": "SQafHvoFPuB57NmBD" }] }'
```

## Example Result

```javascript
{
  "department": {
    "enabled": false,
    "name": "new from api",
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:22:19.109Z",
    "_id": "iTfLCX3qqwKgf5uqg"
  },
  "agents": [
    {
      "agentId": "SQafHvoFPuB57NmBD",
      "count": 0,
      "order": 0,
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description                       |
| ------- | --------------------------------- |
| 1.0.0   | New fields for department updated |
| 0.42.0  | Added                             |

##
