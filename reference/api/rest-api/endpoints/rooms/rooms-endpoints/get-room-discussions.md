# Get Room Discussions

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.getDiscussions</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") and the[#query-and-fields](../../../#query-and-fields "mention") parameters. Additional parameters are as follows:

<table><thead><tr><th width="227.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>general</code></td><td>The room ID or name. You must enter at least one of the parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.getDiscussions?roomId=GENERAL
```

## Example Response

```json
{
    "discussions": [
        {
            "_id": "hthLkno5RqTyNna4H",
            "name": "8BRnQEJQM8MjJWxkJ",
            "fname": "general discussion",
            "t": "p",
            "msgs": 1,
            "usersCount": 1,
            "u": {
                "_id": "rocketchat.internal.admin.test",
                "username": "rocketchat.internal.admin.test"
            },
            "topic": "general",
            "prid": "GENERAL",
            "ts": "2019-04-03T01:01:36.286Z",
            "ro": false,
            "sysMes": true,
            "default": false,
            "_updatedAt": "2019-04-03T01:01:36.402Z",
            "lastMessage": {
                "msg": "test",
                "ts": "2019-04-03T01:01:36.339Z",
                "u": {
                    "_id": "rocketchat.internal.admin.test",
                    "username": "rocketchat.internal.admin.test",
                    "name": "RocketChat Internal Admin Test"
                },
                "rid": "hthLkno5RqTyNna4H",
                "_id": "LLoaxBR8A7M24Qiji",
                "_updatedAt": "2019-04-03T01:01:36.368Z",
                "mentions": [],
                "channels": []
            },
            "lm": "2019-04-03T01:01:36.339Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
