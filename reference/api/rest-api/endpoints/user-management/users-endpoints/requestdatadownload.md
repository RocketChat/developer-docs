# Request Data Download

<table><thead><tr><th width="166">HTTP Method</th><th width="367">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.requestDataDownload</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="193.33333333333331">Key</th><th width="210">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>fullExport</code></td><td><code>true</code> or <code>false</code></td><td>Whether you want a full export or not. By default, the value is <code>false</code>.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.requestDataDownload
```

## Example Response

```json
{
    "requested": false,
    "exportOperation": {
        "_id": "uDSuaW7vGd9B7j8qD",
        "createdAt": "2019-06-07T23:02:13.359Z",
        "userId": "hjwGZafNqExtFNmN7",
        "roomList": [
            {
                "roomId": "GENERAL",
                "roomName": "general",
                "userId": null,
                "exportedCount": 8,
                "status": "completed",
                "targetFile": "general.html",
                "type": "c"
            }
        ],
        "status": "uploading",
        "exportPath": "/tmp/userData/hjwGZafNqExtFNmN7/partial",
        "assetsPath": "/tmp/userData/hjwGZafNqExtFNmN7/partial/assets",
        "fileList": [],
        "generatedFile": "/tmp/zipFiles/hjwGZafNqExtFNmN7.zip",
        "fullExport": false,
        "_updatedAt": "2019-06-07T23:15:00.326Z"
    },
    "success": true
}
```

## Change Log

| Version | Description                          |
| ------- | ------------------------------------ |
| 1.2.0   | Added as `users.requestDataDownload` |
