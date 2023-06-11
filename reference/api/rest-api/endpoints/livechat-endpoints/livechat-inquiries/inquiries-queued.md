---
description: Lists queued inquiries
---

# Inquiries Queued

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.queued` | `yes` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/inquiries.queued
```

## Example Result

```javascript
{
    "inquiries": [
        {
            "_id": "xn5sKBatdkgDfjDLC",
            "rid": "8AuphbFBSNBjeZQFs",
            "name": "hk",
            "ts": "2021-07-22T14:28:57.987Z",
            "department": "CAJioQNAvLnYWTy8i",
            "message": "",
            "status": "queued",
            "v": {
                "_id": "hPF84vuahYBZugM8L",
                "username": "guest-535",
                "token": "zdynf0a9vsiiiq1dlf9abf",
                "status": "offline"
            },
            "t": "l",
            "queueOrder": 1,
            "estimatedWaitingTimeQueue": 0,
            "estimatedServiceTimeAt": "2021-07-22T14:28:57.987Z",
            "_updatedAt": "2021-07-22T14:37:28.470Z"
        },
        {
            "_id": "g6FY2B8PNwneteRG9",
            "rid": "iZ7XDSgcjBgczqko9",
            "name": "hk",
            "ts": "2021-07-22T14:28:07.350Z",
            "department": "CAJioQNAvLnYWTy8i",
            "message": "",
            "status": "queued",
            "v": {
                "_id": "ycwLFcaH4ey9XYYvu",
                "username": "guest-534",
                "token": "ili20miimhh8x33ld0b5de",
                "status": "offline"
            },
            "t": "l",
            "queueOrder": 1,
            "estimatedWaitingTimeQueue": 0,
            "estimatedServiceTimeAt": "2021-07-22T14:28:07.350Z",
            "_updatedAt": "2021-07-22T14:28:24.521Z"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```



