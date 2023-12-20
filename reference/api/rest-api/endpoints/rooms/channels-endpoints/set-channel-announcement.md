# Set Channel Announcement

Sets the announcement for the channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.setAnnouncement</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="216.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>announcement</code><mark style="color:red;"><code>*</code></mark></td><td><code>Test out everything.</code></td><td>The announcement to set for the channel.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setAnnouncement \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "announcement": "Test out everything" }'
```

## Example Result

```json
{
  "announcement": "Test out everything",
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.63.0  | Added       |
