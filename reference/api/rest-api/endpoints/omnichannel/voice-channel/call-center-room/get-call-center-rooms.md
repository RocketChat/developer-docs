---
description: To retrieve a list of VoIP rooms
---

# Get Call Center Rooms

| **URL**          | **Requires Authentication** | **HTTP Method** |
| ---------------- | --------------------------- | --------------- |
| `/v1/voip/rooms` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Example**    | **Required** | **Description**                             |
| ------------ | -------------- | ------------ | ------------------------------------------- |
| `agents`     | `string[]`     | No           | A list of agent information                 |
| `Open`       | `true \|false` | No           | The status of the room                      |
| `createdAt`  | `string`       | No           | The date and time when the room was created |
| `closedAt`   | `string`       | No           | The date and time when the room was closed  |
| `tags`       | `string[]`     | No           | A list of tag information                   |
| `queue`      | `string`       | No           | The ID assigned to the call (opaque ID)     |
| `visitorId`  | `string`       | No           | The unique identifier for the visitor       |

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl -X GET\
     -H "Content-type:application/json" \
     http://localhost:3000/api//v1/voip/rooms \
     -d '{"open": true }'
```

### Example Result

```json
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
    "success": true
}
```

### Error Response

401 Unauthorized
