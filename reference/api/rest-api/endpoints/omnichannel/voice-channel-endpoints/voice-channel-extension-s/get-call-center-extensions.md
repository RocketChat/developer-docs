# Get List of Call Center Extensions

<table><thead><tr><th width="163">HTTP Method</th><th width="343">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/omnichannel/extensions</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-agent-extension-association`
{% endhint %}

## Query Parameters

This endpoint supports the optional `count` and `offset` [#pagination](../../../../#pagination "mention") parameters. Additional parameters are as follows:

<table><thead><tr><th width="212.33333333333331">Key</th><th width="210">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>status</code></td><td><code>free</code></td><td>The status of the extension.</td></tr><tr><td><code>agentId</code></td><td><code>dBHdm2R4gf</code></td><td>The agent ID.</td></tr><tr><td><code>queues</code></td><td><code>DevTest</code></td><td>The queues associated with the extension.</td></tr><tr><td><code>extension</code></td><td><code>700009</code></td><td>Extension number.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'localhost:3000/api/v1/omnichannel/extensions?count=10&offset=10' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json'
```
{% endcode %}

## Example Response

```json
{
    "success": true
}
```
