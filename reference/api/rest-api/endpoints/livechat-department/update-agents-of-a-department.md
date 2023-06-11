---
description: Update agents of a department
---

# Update agents of a department

| URL                                               | Requires Auth | HTTP Method |
| ------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/department/:departmentId/agents` | `YES`         | `Post`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument       | Example             | Required |               |
| -------------- | ------------------- | -------- | ------------- |
| `departmentId` | `CAJioQNAvLnYWTy8i` | Required | Department Id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department/:departmentId/agents\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example payload

```javascript
{
    "upsert": [{
    "agentId": "fasdfav22fas",
    "username": "username22",
    "count": 20000,
    "order": 20000
    }],
"remove": []
}
```

## Result

```javascript
{
    "success": true
}
```

{% hint style="info" %}
When called, the agents in "upsert" will be assigned to the department (in the URL param). In case the agents are already there, their information will be updated. The agents in the "remove" key will be unassigned from the department.
{% endhint %}
