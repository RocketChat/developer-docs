---
description: Retrieves visitor info by ID
---

# Visitor info by ID

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.info` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| visitorId | `yAivGTq4FcsjpvsdB` | Required | Livechat visitor id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.info?visitorId=yAivGTq4FcsjpvsdB \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "visitor": {
        "_id": "yAivGTq4FcsjpvsdB",
        "username": "guest-536",
        "ts": "2021-07-22T14:42:34.076Z",
        "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Safari/537.36",
        "ip": "72.255.57.255",
        "host": "multiverse.rocket.chat",
        "_updatedAt": "2021-07-22T14:42:40.271Z",
        "department": "CAJioQNAvLnYWTy8i",
        "name": "low",
        "token": "io5srgou19520h67ex4i2",
        "visitorEmails": [
            {
                "address": "low@gmail.com"
            }
        ],
        "lastChat": {
            "_id": "myPNwjZr4z27Mi7qW",
            "ts": "2021-07-22T14:42:40.271Z"
        }
    },
    "success": true
}
```

