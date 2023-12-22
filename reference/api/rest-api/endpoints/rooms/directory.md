# Directory

The endpoint searches by users or channels on all users and channels available on the workspace.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/directory</code></td><td><a href="../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../#pagination "mention") parameters, alongside the[#query-and-fields](../../#query-and-fields "mention") parameters.

## Body Parameters

<table><thead><tr><th width="169.33333333333331">Key</th><th width="257">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code><mark style="color:red;"><code>*</code></mark></td><td><code>{"text": "rocket", "type": "users", "workspace": "local"}</code></td><td>When <code>type</code> is <code>users</code>, you can send an additional <code>workspace</code> field, that can be <code>local</code> (default) or <code>all</code>. <code>workspace=all</code> will work only if <a href="../settings/federation-endpoints/">Federation</a> is enabled.</td></tr></tbody></table>

## Example Call

```bash
curl -G -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
          -H "X-User-Id: hw5DThnhQmxDWnavu" \
          -H "Content-type: application/json" \
          http://localhost:3000/api/v1/directory \
          --data-urlencode 
                    'query={"text": "rocket", "type": "users", "workspace": "local"}'
```

## Example Response

```javascript
{
    "result": [
        {
            "_id": "jRca8kibJx8NkLJxt",
            "createdAt": "2018-04-13T12:46:26.517Z",
            "emails": [
                {
                    "address": "user.test.1523623548558@rocket.chat",
                    "verified": false
                }
            ],
            "name": "EditedRealNameuser.test.1523623548558",
            "username": "editedusernameuser.test.1523623548558",
            "avatarETag": "6YbLtc4v9b4conXon"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description                                         |
| ------- | --------------------------------------------------- |
| 1.0.0   | Added `workspace` query param                       |
| 0.65.0  | Added Pagination fields: `count`, `total`, `offset` |
| 0.64.0  | Added                                               |
