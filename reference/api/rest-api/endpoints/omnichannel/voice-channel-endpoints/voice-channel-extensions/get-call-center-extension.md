# Get Call Center Extension

<table><thead><tr><th width="163">HTTP Method</th><th width="343">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/omnichannel/extension</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-agent-extension-association`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="180.33333333333331">Key</th><th width="222">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>2hzS2maZM39wGggdd</code></td><td>The value of the user ID or the user name.</td></tr><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>free</code></td><td><p>The type of extension. The values can be:</p><ul><li><code>free</code></li><li><code>allocated</code></li><li><code>available</code></li></ul></td></tr></tbody></table>

## Example Call

```powershell
curl --location --request GET 'localhost:3000/api/v1/omnichannel/extension? \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "userId": "2hzS2maZM39wGggdd",
    "type": "free"
}'
```

## Example Response

```json
{
    "extensions": "10023"
}
```
