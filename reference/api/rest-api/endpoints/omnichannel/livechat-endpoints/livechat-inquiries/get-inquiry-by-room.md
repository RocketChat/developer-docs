# Get Inquiry by Room

<table><thead><tr><th width="163">HTTP Method</th><th width="363">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/inquiries.getOne</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="187.33333333333331">Key</th><th width="238">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.getOne?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
    "inquiry": {
        "_id": "6560940c6a1ef5b1a2bf9324",
        "rid": "yy8SmYKfHQ6GZdnJp",
        "name": "kookie",
        "ts": "2023-11-24T12:16:12.370Z",
        "message": "",
        "status": "taken",
        "v": {
            "_id": "656090576a1ef5b1a2bf919b",
            "username": "guest-51",
            "token": "38cc8c765bf77e943f6e4319c5891f6c04",
            "status": "online",
            "activity": [
                "2023-11"
            ]
        },
        "t": "l",
        "priorityWeight": 99,
        "estimatedWaitingTimeQueue": 9999999,
        "source": {
            "type": "widget"
        },
        "_updatedAt": "2023-11-24T12:27:43.852Z",
        "lastMessage": {
            "_id": "Hjwmd7bBZTiEXrywn",
            "rid": "yy8SmYKfHQ6GZdnJp",
            "msg": "hello",
            "ts": "2023-11-24T12:27:43.474Z",
            "u": {
                "_id": "CkCPNcvsvCDfmWLqC",
                "username": "test.cat",
                "name": "testCat"
            },
            "_updatedAt": "2023-11-24T12:27:43.820Z",
            "urls": [],
            "mentions": [],
            "channels": [],
            "md": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "hello"
                        }
                    ]
                }
            ]
        },
        "takenAt": "2023-11-24T12:18:19.012Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
