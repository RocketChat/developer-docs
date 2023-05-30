---
description: Puts an active livechat conversation on hold
---

# Room Onhold

![](../../../../../../../.gitbook/assets/enterprise.jpg)

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `api/v1/livechat/room.onHold` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example             | Required | Description             |
| -------- | ------------------- | -------- | ----------------------- |
| `roomId` | `Z7223PfNPwH7ihQPh` | Required | Active livechat room id |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/livechat/room.onHold \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d "roomId=Z7223PfNPwH7ihQPh"
```

## Result

```javascript
{
    "success": true
}
```
