---
description: Gives the number of incoming chats (chat rooms) by department
---

# Amount of chat

![](../../../../../../.gitbook/assets/enterprise.jpg)

| URL                                                     | Requires Auth | HTTP Method |
| ------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/analytics/departments/amount-of-chats` | `YES`         | `GET`       |

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
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/amount-of-chats?start=2020-01-10T23:59:22.345Z&end=2021-02-10T23:59:22.345Z \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "rooms": 30,
            "_id": null
        },
        {
            "rooms": 486,
            "_id": "GgYvrkAF63aeQmsh4"
        },
        {
            "rooms": 13,
            "_id": "qajzu7WaBRoQBpq6Z"
        },
        {
            "rooms": 2,
            "_id": "Z2KWYBJQFR7AzfmQL"
        },
        {
            "rooms": 61,
            "_id": "BiqbQav59HD2LzXEY"
        },
        {
            "rooms": 1,
            "_id": "NJaMpSvZFZ4NAXm3j"
        },
        {
            "rooms": 181,
            "_id": "CAJioQNAvLnYWTy8i"
        },
        {
            "rooms": 6,
            "_id": "YiWdMkdbFhk3o9daf"
        },
        {
            "rooms": 10,
            "_id": "8MGLTfaKLCbE9CqR8"
        },
        {
            "rooms": 4,
            "_id": "MpAiP9PMyHwBcmALx"
        },
        {
            "rooms": 51,
            "_id": "Yi87Ju7eTHiZQ7CJt"
        }
    ],
    "count": 11,
    "offset": 0,
    "total": 11,
    "success": true
}
```
