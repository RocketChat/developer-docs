---
description: Gives a list of unit monitors
---

# List of unit monitors

![](../../../../../../../.gitbook/assets/enterprise.jpg)

{% hint style="warning" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-list-of-unit-monitors.md](get-list-of-unit-monitors.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `api/v1/livechat/unitMonitors.list` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/unitMonitors.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "monitors": [
        {
            "_id": "a8RSA5hSzuiKg34PG",
            "monitorId": "gxcJTYapi5mPxuAme",
            "unitId": "sriw2wmP2Zz2pPrre",
            "_updatedAt": "2021-06-28T22:10:01.324Z",
            "username": "Bruno.Solis"
        },
        {
            "_id": "fTayxRuJiRCFfREWc",
            "monitorId": "Nn4ocDJqoJshcoFJi",
            "unitId": "sriw2wmP2Zz2pPrre",
            "_updatedAt": "2021-06-28T22:10:01.329Z",
            "username": "mauricio.pretto"
        },
        {
            "_id": "X2keMaN4WX2zmA99u",
            "monitorId": "cLNSTRsipLCSq7qno",
            "unitId": "sriw2wmP2Zz2pPrre",
            "_updatedAt": "2021-06-28T22:10:01.342Z",
            "username": "milton.rucks"
        }
    ],
    "success": true
}
```
