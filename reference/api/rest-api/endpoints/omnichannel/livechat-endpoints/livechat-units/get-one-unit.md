---
description: Gives the details of a unit
---

# Get one Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-a-unit.md](get-a-unit.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `api/v1/livechat/units.getOne` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `unitId` | `sriw2wmP2Zz2pPrre` | Required | Unit ID     |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units.getOne?unitId=sriw2wmP2Zz2pPrre \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "sriw2wmP2Zz2pPrre",
    "name": "Support",
    "visibility": "public",
    "type": "u",
    "numMonitors": 3,
    "numDepartments": 4,
    "_updatedAt": "2021-06-28T22:10:01.295Z",
    "success": true
}
```
