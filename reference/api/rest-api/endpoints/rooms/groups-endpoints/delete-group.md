# Delete Group

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

Only one of `roomId` or `roomName` is required.

<table><thead><tr><th width="178">Key</th><th width="244">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>general</code></td><td>The channel's name.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.delete \
     -d '{ 
          "roomName": "channelname" }'
```

## Example Result

```json
{
   "success": true
}
```

## Change Log

| Version | Description              |
| ------- | ------------------------ |
| 0.71.0  | Removed `group` property |
| 0.49.0  | Added                    |
