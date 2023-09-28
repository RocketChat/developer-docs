---
description: Gives a list of priorities
---

# List of Priorities

<figure><img src="../../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
![](../../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-priorities.md](get-priorities.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `livechat/priorities.list` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "priorities": [
        {
            "_id": "kihPsGwKWTzf9amQk",
            "name": "High",
            "description": "High",
            "dueTimeInMinutes": 1,
            "_updatedAt": "2020-12-04T19:10:36.875Z"
        },
        {
            "_id": "4WcmeBE4spXx6AxrC",
            "name": "Low",
            "description": "Low",
            "dueTimeInMinutes": 3,
            "_updatedAt": "2020-10-06T22:33:58.571Z"
        },
        {
            "_id": "7Hu352k892rNh45j9",
            "name": "Medium",
            "description": "Medium",
            "dueTimeInMinutes": 2,
            "_updatedAt": "2020-10-06T22:33:40.768Z"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```
