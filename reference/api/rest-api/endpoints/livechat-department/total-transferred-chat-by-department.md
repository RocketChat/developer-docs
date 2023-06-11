---
description: Gives the total of transferred chats by department
---

# Total transferred chat by department

![](../../../../../../../.gitbook/assets/enterprise.jpg)

| URL                                                             | Requires Auth | HTTP Method |
| --------------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/analytics/departments/total-transferred-chats` | `YES`         | `GET`       |

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
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/total-transferred-chats?start=2020-09-10T23:59:22.345Z&end=2021-09-10T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "numberOfTransferredRooms": 62,
            "_id": "GgYvrkAF63aeQmsh4"
        },
        {
            "numberOfTransferredRooms": 6,
            "_id": "Yi87Ju7eTHiZQ7CJt"
        },
        {
            "numberOfTransferredRooms": 10,
            "_id": "sLYp3ry7CRizaP3rJ"
        },
        {
            "numberOfTransferredRooms": 6,
            "_id": "BiqbQav59HD2LzXEY"
        },
        {
            "numberOfTransferredRooms": 27,
            "_id": "CAJioQNAvLnYWTy8i"
        },
        {
            "numberOfTransferredRooms": 1,
            "_id": "8MGLTfaKLCbE9CqR8"
        }
    ],
    "count": 6,
    "offset": 0,
    "total": 6,
    "success": true
}
```
