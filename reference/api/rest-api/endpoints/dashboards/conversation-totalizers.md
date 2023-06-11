---
description: Retrieves conversation totalizers for a department
---

# Conversation Totalizers

| URL                                                            | Requires Auth | HTTP Method |
| -------------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/analytics/dashboards/conversation-totalizers` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument       | Example                    | Required | Description      |
| -------------- | -------------------------- | -------- | ---------------- |
| `departmentId` | `CAJioQNAvLnYWTy8i`        | Required | Business Hour ID |
| `start`        | `2021-07-20T19:00:00.000Z` | Required | Start Time       |
| `end`          | `2021-07-21T18:59:59.000Z` | Required | End Time         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/dashboards/conversation-totalizers?departmentId=CAJioQNAvLnYWTy8i&start=2021-07-20T19:00:00.000Z&end=2021-07-21T18:59:59.000Z \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "totalizers": [
        {
            "title": "Total_conversations",
            "value": 0
        },
        {
            "title": "Open_conversations",
            "value": 0
        },
        {
            "title": "Total_messages",
            "value": 0
        },
        {
            "title": "Total_visitors",
            "value": 0
        }
    ],
    "success": true
}
```
