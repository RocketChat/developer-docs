# Get Omnichannel Agent Extension

Get the extension information associated with the agent.

<table><thead><tr><th width="163">HTTP Method</th><th width="343">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/omnichannel/agent/extension/</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-agent-extension-association`
{% endhint %}

## Path Variables

<table><thead><tr><th width="189.33333333333331">Key</th><th width="227">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>agent5</code></td><td>The user name of the agent.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/omnichannel/agent/extension/agent5' \
--header 'X-Auth-Token: NcQtu58azANDJ1FIpJVg4GqhK9h-j61l' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "success": true
}
```
