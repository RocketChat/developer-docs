---
description: Retrieves agent's statuses chart
---

# Agents Statuses Chart

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/analytics/dashboards/charts/agents-status` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/api/v1/livechat/analytics/dashboards/charts/agents-status\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": null,
    "offline": 78,
    "away": 5,
    "busy": 0,
    "available": 3,
    "success": true
}
```

