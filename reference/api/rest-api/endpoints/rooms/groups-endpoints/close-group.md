# Close Group

Removes the group/channel from the user's list of groups, only if you're part of the group.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.close</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="191">Key</th><th width="258">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>HyehQjC44FwMeiLbX</code></td><td>The groups ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.close \
     -d '{ 
          "roomId": "HyehQjC44FwMeiLbX" }'
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
| 0.48.0  | Added       |
