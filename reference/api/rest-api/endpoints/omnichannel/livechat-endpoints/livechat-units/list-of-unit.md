---
description: Gives a list of units
---

# List of Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-units.md](get-units.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/livechat/units.list` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "units": [
        {
            "_id": "sriw2wmP2Zz2pPrre",
            "name": "Support",
            "visibility": "public",
            "type": "u",
            "numMonitors": 3,
            "numDepartments": 4,
            "_updatedAt": "2021-06-28T22:10:01.295Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
