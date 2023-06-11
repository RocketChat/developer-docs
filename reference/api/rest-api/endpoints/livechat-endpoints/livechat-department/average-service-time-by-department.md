---
description: Returns average of service time chats by department
---

# Average service time by department

![](../../../../../../.gitbook/assets/enterprise.jpg)

| URL                                                          | Requires Auth | HTTP Method |
| ------------------------------------------------------------ | ------------- | ----------- |
| `api/v1/livechat/analytics/departments/average-service-time` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `start`  | `2020-09-09T00:11:22.345Z` | Required | start date  |
| `end`    | `2021-09-10T23:59:22.345Z` | Required | end date    |

{% hint style="info" %}
The API will return a blank page if the correct headers are not sent
{% endhint %}

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/average-service-time?start=2020-09-09T00:11:22.345Z&end=2021-09-09T00:11:22.345Z \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "_id": "CAJioQNAvLnYWTy8i",
            "averageServiceTimeInSeconds": 1920
        },
        {
            "_id": "GgYvrkAF63aeQmsh4",
            "averageServiceTimeInSeconds": 3583
        },
        {
            "_id": "sLYp3ry7CRizaP3rJ",
            "averageServiceTimeInSeconds": 2941
        },
        {
            "_id": "BiqbQav59HD2LzXEY",
            "averageServiceTimeInSeconds": 5831
        },
        {
            "_id": null,
            "averageServiceTimeInSeconds": 3892998
        },
        {
            "_id": "Yi87Ju7eTHiZQ7CJt",
            "averageServiceTimeInSeconds": 1205
        },
        {
            "_id": "4LCeYmCHHnQ3EDBgf",
            "averageServiceTimeInSeconds": 755
        },
        {
            "_id": "8MGLTfaKLCbE9CqR8",
            "averageServiceTimeInSeconds": 1635
        }
    ],
    "count": 8,
    "offset": 0,
    "total": 8,
    "success": true
}
```
