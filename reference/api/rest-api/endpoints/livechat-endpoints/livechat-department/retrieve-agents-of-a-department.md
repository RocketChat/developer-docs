---
description: Returns agents of a specific department
---

# Retrieve agents of a department

| URL                                               | Requires Auth | HTTP Method |
| ------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/department/:departmentId/agents` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument       | Example             | Required | Description   |
| -------------- | ------------------- | -------- | ------------- |
| `departmentId` | `BiqbQav59HD2LzXEY` | Required | Department ID |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department/:departmentId/agents \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "agents": [
        {
            "_id": "SWugWdHhcTX4G2NAP",
            "agentId": "rocket.cat",
            "departmentId": "BiqbQav59HD2LzXEY",
            "_updatedAt": "2021-07-14T14:58:01.013Z",
            "count": 17,
            "departmentEnabled": true,
            "order": 0,
            "username": "rocket.cat"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
