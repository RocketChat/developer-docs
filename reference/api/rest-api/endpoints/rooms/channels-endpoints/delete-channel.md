# Delete Channel

Remove a public channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="181.33333333333331">Key</th><th width="244">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>general</code></td><td>The channel ID or name that you want to delete. You must enter at least one of the parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.delete \
     -d '{ 
          "roomName": "channelname" }'
```

## Example Response

```json
{
   "success": true
}
```

## Change Log

<table><thead><tr><th width="353">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.71.0</td><td>Removed <code>channel</code> property</td></tr><tr><td>0.49.0</td><td>Added</td></tr></tbody></table>
