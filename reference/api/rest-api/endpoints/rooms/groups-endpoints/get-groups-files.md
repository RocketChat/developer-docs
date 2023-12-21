# Get Groups Files

Retrieves the files from a group/channel.&#x20;

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.files</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters, alongside the[#query-and-fields](../../../#query-and-fields "mention") parameters.

<table><thead><tr><th width="212.33333333333331">Key</th><th width="222">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or  <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> <br><code>test</code></td><td>The room ID or the room name.</td></tr></tbody></table>

## Example Call

With the `roomId` parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.files?roomId=ByehQjC44FwMeiLbX
```

With the `roomName` parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.files?roomName=test
```

## Example Response

```json
{
    "files": [
        {
            "_id": "S78TNnvaWGwdYRaCD",
            "name": "images.jpeg",
            "size": 9778,
            "type": "image/jpeg",
            "rid": "GENERAL",
            "description": "",
            "store": "GridFS:Uploads",
            "complete": true,
            "uploading": false,
            "extension": "jpeg",
            "progress": 1,
            "user": {
                "_id": "ksKsKmrjvxzkzxkww",
                "username": "rocket.cat",
                "name": "Rocket Cat"
            },
            "_updatedAt": "2018-03-08T14:47:37.003Z",
            "instanceId": "uZG54xuoKauKHykbQ",
            "etag": "jPaviS9qG22xC5sDC",
            "path": "/ufs/GridFS:Uploads/S78TNnvaWGwdYRaCD/images.jpeg",
            "token": "28cAb868d9",
            "uploadedAt": "2018-03-08T14:47:37.295Z",
            "url": "/ufs/GridFS:Uploads/S78TNnvaWGwdYRaCD/images.jpeg"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

<table><thead><tr><th width="340">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.64.0</td><td>Change <code>userId</code> to <code>user</code> object in response</td></tr><tr><td>0.59.0</td><td>Added</td></tr></tbody></table>
