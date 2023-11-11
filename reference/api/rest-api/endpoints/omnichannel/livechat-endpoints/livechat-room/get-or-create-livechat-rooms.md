# Get or Create Livechat Rooms

Get the data of an existing room of a visitor. If a room doesn't exist for the visitor, a new room is created.

<table><thead><tr><th width="163">HTTP Method</th><th width="286">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/room</code></td><td><code>no</code></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="189.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor <code>token</code>.</td></tr><tr><td><code>rid</code></td><td><code>kCJDd5peKiZnGJLPq</code></td><td>The room <code>_id</code>.</td></tr><tr><td><code>agentId</code></td><td><code>XycfA5CetCPuEjqxw</code></td><td>The agent id.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl http://localhost:3000/api/v1/livechat/room?token=8s7e9ony6ctl27e1qf8kue&rid=kCJDd5peKiZnGJLPq&agentId=XycfA5CetCPuEjqxw
```
{% endcode %}

## Example Response

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
