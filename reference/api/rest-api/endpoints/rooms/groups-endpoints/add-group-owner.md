# Add Group Owner

Gives the role of owner for a user in the current group/channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.addOwner</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="191.33333333333331">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>nSYqWzZ4GsKTX4dyK</code></td><td>The user ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.addOwner \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "nSYqWzZ4GsKTX4dyK" }'
```

## Example Response

```json
{
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.49.4  | Added       |
