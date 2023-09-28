---
description: Gives the total of abandoned chats by department
---

# Total abandoned chats by department

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

| URL                                                           | Requires Auth | HTTP Method |
| ------------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/analytics/departments/total-abandoned-chats` | `YES`         | `GET`       |

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

### Notes

* \*\* The API will return a blank page if the correct headers are not sent

## Example Call

```bash
curl --location --request GET 'https://multiverse.rocket.chat/api/v1/livechat/analytics/departments/total-abandoned-chats?start=2020-09-10T23:59:22.345Z&end=2021-09-10T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "abandonedRooms": 3,
            "_id": "4LCeYmCHHnQ3EDBgf"
        },
        {
            "abandonedRooms": 1,
            "_id": "8MGLTfaKLCbE9CqR8"
        },
        {
            "abandonedRooms": 1,
            "_id": "Yi87Ju7eTHiZQ7CJt"
        },
        {
            "abandonedRooms": 77,
            "_id": "GgYvrkAF63aeQmsh4"
        },
        {
            "abandonedRooms": 12,
            "_id": "sLYp3ry7CRizaP3rJ"
        },
        {
            "abandonedRooms": 12,
            "_id": "BiqbQav59HD2LzXEY"
        },
        {
            "abandonedRooms": 6,
            "_id": "CAJioQNAvLnYWTy8i"
        }
    ],
    "count": 7,
    "offset": 0,
    "total": 7,
    "success": true
}
```

## Change Log
