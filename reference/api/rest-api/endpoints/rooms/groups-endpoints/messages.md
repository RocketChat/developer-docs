# Get Group Messages

Lists all of the specific groups/channels messages on the server.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.messages</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters, alongside the[#query-and-fields](../../../#query-and-fields "mention") parameters.

<table><thead><tr><th width="195">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID. The parameter is required if <code>roomName</code> is not provided.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>testGroup</code></td><td>The group name. The parameter is required if <code>roomId</code> is not provided.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.messages?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
    "messages": [
        {
            "_id": "CeXwh5eBbdrtvnqG6",
            "rid": "agh2Sucgb54RQ8dDo",
            "msg": "s",
            "ts": "2018-10-05T13:48:21.616Z",
            "u": {
                "_id": "KPkEYwKKBKZnEEPpt",
                "username": "marcos.defendi",
                "name": "Marcos Defendi"
            },
            "_updatedAt": "2018-10-05T13:48:49.535Z",
            "reactions": {
                ":frowning2:": {
                    "usernames": [
                        "marcos.defendi"
                    ]
                }
            },
            "mentions": [],
            "channels": [],
            "starred": {
                "_id": "KPkEYwKKBKZnEEPpt"
            }
        },
        {
            "_id": "MrAeupRiF9TvhMesK",
            "t": "room_changed_privacy",
            "rid": "agh2Sucgb54RQ8dDo",
            "ts": "2018-10-05T00:11:16.998Z",
            "msg": "Private Group",
            "u": {
                "_id": "rocketchat.internal.admin.test",
                "username": "rocketchat.internal.admin.test"
            },
            "groupable": false,
            "_updatedAt": "2018-10-05T00:11:16.998Z"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.59.0  | Added       |
