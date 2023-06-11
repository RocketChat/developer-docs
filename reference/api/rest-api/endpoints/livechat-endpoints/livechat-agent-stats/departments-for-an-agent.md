---
description: Returns all the departments associated with an agent.
---

# Agent's Departments

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/agents/:agentId/departments` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## URL Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `agentId` | `XycfA5CetCPuEjqxw` | Required | Agent ID |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/agents/:agentId/departments \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "_id": "R34ZLL6wxDuk4S29G",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "_updatedAt": "2021-06-29T16:09:12.897Z",
            "count": 0,
            "departmentEnabled": true,
            "order": 0,
            "username": "faria.masood"
        },
        {
            "_id": "4TnnwbRsBY2upkzjp",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "GgYvrkAF63aeQmsh4",
            "_updatedAt": "2021-06-29T16:09:12.918Z",
            "count": 0,
            "departmentEnabled": true,
            "order": 0,
            "username": "faria.masood"
        },
        {
            "_id": "wJTwJsAxRcZ8nc9sB",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "Yi87Ju7eTHiZQ7CJt",
            "_updatedAt": "2021-06-29T16:09:12.937Z",
            "count": 0,
            "departmentEnabled": false,
            "order": 0,
            "username": "faria.masood"
        },
        {
            "_id": "ccjbvLEREZ6vwjBFk",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "sLYp3ry7CRizaP3rJ",
            "_updatedAt": "2021-06-29T16:09:12.956Z",
            "count": 0,
            "departmentEnabled": false,
            "order": 0,
            "username": "faria.masood"
        }
    ],
    "success": true
}
```

