---
description: Retrieve the conversation transfer history from one department to another.
---

# Livechat Transfer

| URL                                     | Requires Auth | HTTP Method |
| --------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/transfer.history/:rid` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

| Argument | Example             | Required | Description     |
| -------- | ------------------- | -------- | --------------- |
| `rid`    | `zRAeTszXor8CCPceB` | Required | The room `_id`. |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/transfer.history/:rid\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "history": [],
    "count": 0,
    "offset": 0,
    "total": 0,
    "success": true
}
```
