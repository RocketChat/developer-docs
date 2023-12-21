# Get Group Roles

Lists all user's roles in the group/channel.

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.roles</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="195.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID. The parameter is required if <code>roomName</code> is not provided.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>general</code></td><td>The group name. The parameter is required if the <code>roomId</code> is not provided.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.roles?roomId=ByehQjC44FwMeiLbX
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
