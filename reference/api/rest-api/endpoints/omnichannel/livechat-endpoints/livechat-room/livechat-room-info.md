---
description: Get the Livechat room data or open a new room.
---

# Livechat Room Info

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/livechat/room` | `no`          | `GET`       |

## Query Parameters

| Argument  | Example             | Required | Description          |
| --------- | ------------------- | -------- | -------------------- |
| `token`   | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |
| `rid`     | `kCJDd5peKiZnGJLPq` | Optional | The room `_id`.      |
| `agentId` | `XycfA5CetCPuEjqxw` | Optional | The agent id.        |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/room?token=8s7e9ony6ctl27e1qf8kue&rid=kCJDd5peKiZnGJLPq&agentId=XycfA5CetCPuEjqxw
```

## Example Result

```javascript
{
    "room": {
        "_id": "kCJDd5peKiZnGJLPq",
        "fname": "Mary",
        "t": "l",
        "v": {
            "_id": "47Dajwh9DjpnTAugW",
            "username": "guest-165",
            "token": "8s7e9ony6ctl27e1qf8kue",
            "status": "offline",
            "lastMessageTs": "2021-07-09T20:20:58.755Z"
        },
        "departmentId": "CAJioQNAvLnYWTy8i",
        "default": false,
        "ro": false,
        "sysMes": true,
        "open": true,
        "msgs": 7,
        "ts": "2021-07-09T20:12:19.795Z",
        "_updatedAt": "2021-07-09T20:21:07.334Z",
        "lm": "2021-07-09T20:20:58.755Z",
        "customFields": {
            "salesforceCrmContactId": "0032y000009mtOIAAY"
        },
        "usersCount": 2,
        "cl": false,
        "departmentAncestors": [
            "sriw2wmP2Zz2pPrre"
        ],
        "lastMessage": {
            "_id": "SgrsSm3HNGrG5xTmk",
            "rid": "kCJDd5peKiZnGJLPq",
            "msg": "d",
            "token": "8s7e9ony6ctl27e1qf8kue",
            "alias": "Mary",
            "ts": "2021-07-09T20:20:58.755Z",
            "u": {
                "_id": "47Dajwh9DjpnTAugW",
                "username": "guest-165",
                "name": "Mary"
            },
            "_updatedAt": "2021-07-09T20:20:58.896Z",
            "urls": [],
            "mentions": [],
            "channels": [],
            "md": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "d"
                        }
                    ]
                }
            ],
            "newRoom": false,
            "showConnecting": true
        },
        "metrics": {
            "reaction": {
                "fd": "2021-07-09T20:19:53.243Z",
                "ft": 23.821,
                "tt": 24.006
            },
            "response": {
                "avg": 226.4365,
                "fd": "2021-07-09T20:19:53.243Z",
                "ft": 452.688,
                "total": 2,
                "tt": 452.873
            },
            "v": {
                "lq": "2021-07-09T20:20:58.755Z"
            },
            "servedBy": {
                "lr": "2021-07-09T20:19:53.077Z"
            }
        },
        "servedBy": {
            "_id": "XycfA5CetCPuEjqxw",
            "username": "faria.masood",
            "ts": "2021-07-09T20:19:29.422Z"
        },
        "waitingResponse": true
    },
    "newRoom": false,
    "success": true
}
```
