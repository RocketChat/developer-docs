# Set Group Purpose

Sets the description for the group/channel (the same as `groups.setDescription`, obsolete).

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.setPurpose</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="173">Key</th><th width="259">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>purpose</code><mark style="color:red;"><code>*</code></mark></td><td><code>Test out everything</code></td><td>The description to set for the group.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.setPurpose \
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
