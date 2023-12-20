# Get Channel Roles

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.roles</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="188">Key</th><th width="230">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID or name. You must enter at least one of the parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.roles?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
    "roles": [
        {
            "rid": "BaE62jfDLXK3Xo6BA",
            "u": {
               "_id": "BkNkw3iKgNyhMbPyW",
               "username": "ronnie.dio",
               "name": "Ronnie James Dio"
            },
            "roles": [
               "moderator"
            ],
            "_id": "ehPuGyZBedznJsQHp"
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.65.0  | Added       |
