# Set Group Topic

Sets the topic for the group/channel.

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.setTopic</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="185.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>topic</code><mark style="color:red;"><code>*</code></mark></td><td><code>Discuss all of the testing</code></td><td>The group topic to set.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.setTopic \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "topic": "Discuss all of the testing" }'
```

## Example Response

```json
{
  "topic": "Discuss all of the testing",
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
