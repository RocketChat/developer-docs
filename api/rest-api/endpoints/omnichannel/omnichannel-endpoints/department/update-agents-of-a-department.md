---
description: Update agents of a department
---

# Update agents of a department

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/department/:departmentId/agents` | `YES` | `Post` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Query Parameters

| Argument | Example | Required |  |
| :--- | :--- | :--- | :--- |
| `departmentId` | `CAJioQNAvLnYWTy8i` | Required | Department Id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department/:departmentId/agents\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "success": true
}
```

