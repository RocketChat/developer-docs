# Get info about a department

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/department/:_id` | `yes`         | `GET`       |

## Payload

| Argument | Example             | Required | Description           |
| -------- | ------------------- | -------- | --------------------- |
| `_id`    | `SQafHvoFPuB57NmBD` | Required | The department `_id`. |

## Query Parameter

| Argument        | Example | Required                   | Description                   |
| --------------- | ------- | -------------------------- | ----------------------------- |
| `includeAgents` | `true`  | Optional(default **true**) | If agents should be included. |

**Note:** The `agents` field will only be returned if the user has the `view-livechat-departments` permission.

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/department/iTfLCX3qqwKgf5uqg
```

## Example Result

```javascript
{
  "department": {
    "_id": "iTfLCX3qqwKgf5uqg",
    "enabled": false,
    "name": "new from api",
    "description": null,
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:22:19.109Z"
  },
  "agents": [
    {
      "_id": "DDjZbhTF74n3NBuWK",
      "agentId": "SQafHvoFPuB57NmBD",
      "departmentId": "iTfLCX3qqwKgf5uqg",
      "username": "john.doe",
      "count": 0,
      "order": 0,
      "_updatedAt": "2016-12-13T17:22:19.169Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description                           |
| ------- | ------------------------------------- |
| 2.2.0   | Added `includeAgents` query parameter |
| 0.42.0  | Added                                 |

##
