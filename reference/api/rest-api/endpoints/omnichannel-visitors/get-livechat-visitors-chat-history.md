---
description: Get livechat visitor's chat history
---

# Get livechat visitor's chat history

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## URL Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `hhMKhHnnbY79mGs9K` | Required | Livechat room id |
| `visitorId` | `QyBAKC5Wc8tcv6cco` | Required | Livechat visitor id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "history": [
        {
            "_id": "hhMKhHnnbY79mGs9K",
            "msgs": 2,
            "usersCount": 1,
            "lm": "2021-07-22T17:17:04.937Z",
            "fname": "Maria",
            "t": "l",
            "ts": "2021-07-22T17:17:04.216Z",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "v": {
                "_id": "QyBAKC5Wc8tcv6cco",
                "username": "guest-537",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "status": "online",
                "lastMessageTs": "2021-07-22T17:17:04.937Z"
            },
            "cl": false,
            "open": true,
            "_updatedAt": "2021-07-22T17:17:05.078Z",
            "departmentAncestors": [
                "sriw2wmP2Zz2pPrre"
            ],
            "lastMessage": {
                "_id": "YfrxZ6gmaYLpPTxFP",
                "rid": "hhMKhHnnbY79mGs9K",
                "msg": "hi",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "alias": "Maria",
                "ts": "2021-07-22T17:17:04.937Z",
                "u": {
                    "_id": "QyBAKC5Wc8tcv6cco",
                    "username": "guest-537",
                    "name": "Maria"
                },
                "unread": true,
                "_updatedAt": "2021-07-22T17:17:05.044Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "hi"
                            }
                        ]
                    }
                ],
                "newRoom": false,
                "showConnecting": true
            },
            "metrics": {
                "reaction": {
                    "fd": "2021-07-22T17:17:04.449Z",
                    "ft": 0.233,
                    "tt": 0.233
                },
                "response": {
                    "avg": 0.233,
                    "fd": "2021-07-22T17:17:04.449Z",
                    "ft": 0.233,
                    "total": 1,
                    "tt": 0.233
                },
                "v": {
                    "lq": "2021-07-22T17:17:04.937Z"
                }
            },
            "waitingResponse": true
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

