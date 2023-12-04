# Get List of Call Center Rooms

<table><thead><tr><th width="163">HTTP Method</th><th width="334">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/rooms</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* For an admin: `view-livechat-rooms`
* For an agent: `view-l-room`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention") and [#query-and-fields](../../../../#query-and-fields "mention") parameters. Additional optional parameters are as follows:

<table><thead><tr><th width="191.33333333333331">Key</th><th width="210">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>agents</code></td><td><code>string[]</code></td><td>List of agent information.</td></tr><tr><td><code>open</code></td><td><code>true</code></td><td>The status of the room. The value can be <code>true</code> or <code>false</code>.</td></tr><tr><td><code>createdAt</code></td><td><code>2021-07-09T20:20:58.755Z</code></td><td>The date and time when the room was created.</td></tr><tr><td><code>closedAt</code></td><td><code>2021-07-09T21:20:58.755Z</code></td><td>The date and time when the room was closed.</td></tr><tr><td><code>tags</code></td><td><code>string[]</code></td><td>List of tag information.</td></tr><tr><td><code>queue</code></td><td><code>string</code></td><td>The ID assigned to the call (opaque ID).</td></tr><tr><td><code>visitorId</code></td><td><code>47Dajwh9DjpnTAugW</code></td><td>The visitor ID.</td></tr><tr><td><code>direction</code></td><td><code>inbound</code></td><td>The direction of the call.</td></tr><tr><td><code>roomName</code></td><td><code>Missing key</code></td><td>The name of the room.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

```powershell
curl -X GET\
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/voip/rooms \
     -d '{"open": true }'
```

## Example Response

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
            "username": "kim.jane",
            "ts": "2021-07-09T20:19:29.422Z"
        },
        "waitingResponse": true
    },
    "success": true
}
```
