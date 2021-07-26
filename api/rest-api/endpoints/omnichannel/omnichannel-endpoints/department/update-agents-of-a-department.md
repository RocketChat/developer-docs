---
description: Retrieves agents of a department
---

# Get agents of a department

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/department/:departmentId/agents` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Query Parameters

| Argument | Example | Required |  |
| :--- | :--- | :--- | :--- |
| `departmentId` | `CAJioQNAvLnYWTy8i` | Required | Department id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department/:departmentId/agents\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "agents": [
        {
            "_id": "yQQAXh8FPyr8LZtpS",
            "agentId": "AkFjhgJFHAhNK3e6o",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "_updatedAt": "2021-06-23T06:02:48.367Z",
            "count": 0,
            "order": 0,
            "username": "Karina",
            "departmentEnabled": true
        },
        {
            "_id": "kmv6FKPH6eBgHSwfr",
            "agentId": "8BjAbHuhYiQnMaQ2r",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "_updatedAt": "2021-07-21T23:54:35.568Z",
            "count": 0,
            "departmentEnabled": true,
            "order": 0,
            "username": "aaron.ogle"
        },
        
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

