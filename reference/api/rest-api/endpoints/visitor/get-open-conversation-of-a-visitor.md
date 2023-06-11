---
description: Retrieve open conversations associated with a particular visitor
---

# Get open conversation of a visitor

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/visitor/:token/room` | `Yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument | Example                  | Required | Description          |
| -------- | ------------------------ | -------- | -------------------- |
| `token`  | `8s7e9ony6ctl27e1qf8kue` | Required | The visitor `token`. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitor/:token/room
```

## Example Result

```javascript
{
    "rooms": [
        {
            "_id": "D2hej3mmvkwyB4HR6",
            "t": "l",
            "cl": false,
            "servedBy": {
                "_id": "XycfA5CetCPuEjqxw",
                "username": "faria.masood",
                "ts": "2021-07-18T11:50:38.822Z"
            }
        }
    ],
    "success": true
}
```
