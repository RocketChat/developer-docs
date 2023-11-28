# List Queued Inquiries

<table><thead><tr><th width="163">HTTP Method</th><th width="363">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/inquiries.queued</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention")query parameters. Other optional parameters are as follows:

<table><thead><tr><th width="197.33333333333331">Key</th><th width="239">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>department</code></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The department ID or name.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/inquiries.queued
```

## Example Response

```json
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
            "name": "dk",
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
