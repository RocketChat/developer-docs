---
description: Get a list of all priorities
---

# Get Priorities

This supports the [Offset, Count, and Sort Query Parameters](../../pagination.md).

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `livechat/priorities` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                             |
| -------------- | -------------- | -------- | ------------------------------------------------------- |
| `X-User-Id`    | `myuser-id`    | Required | Your userId (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)  |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```

## Result

```javascript
{
    "priorities": [
        {
            "_id": "e6pjPYF4pFWr7g59F",
            "name": "high",
            "dueTimeInMinutes": 1,
            "_updatedAt": "2022-10-04T13:48:21.016Z",
            "description": "high"
        },
        {
            "_id": "5PMgshbQWsoHsYy2c",
            "name": "medium",
            "dueTimeInMinutes": 6,
            "_updatedAt": "2022-09-01T13:51:20.710Z"
        },
        {
            "_id": "idQkJgzTND3gBRNWJ",
            "name": "low",
            "description": "test",
            "dueTimeInMinutes": 2,
            "_updatedAt": "2022-10-04T13:48:07.371Z"
        },
        {
            "_id": "WXbWQSPevAyY2CjRq",
            "name": "low",
            "dueTimeInMinutes": 4,
            "_updatedAt": "2022-09-01T13:51:04.837Z"
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```
