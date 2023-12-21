# Get Group Moderators

Lists all group moderators.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.moderators</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="195">Key</th><th width="228">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID. The parameter is required if <code>roomName</code> is not provided.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>testGroup</code></td><td>The group name. The parameter is required if <code>roomId</code> is not provided.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.moderators?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
    "moderators": [
        {
            "_id": "rocket.cat",
            "username": "rocket.cat",
            "name": Rocket.Cat
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.70.0  | Added       |
