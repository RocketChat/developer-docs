# Channel Set Purpose

Sets the description for the channel (the same as `channels.setDescription`, obsolete).

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.setPurpose</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="192.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>purpose</code><mark style="color:red;"><code>*</code></mark></td><td><code>Test out everything</code></td><td>The description to set for the channel.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setPurpose \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "purpose": "Test out everything" }'
```

## Example Response

```json
{
  "purpose": "Testing out everything",
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
