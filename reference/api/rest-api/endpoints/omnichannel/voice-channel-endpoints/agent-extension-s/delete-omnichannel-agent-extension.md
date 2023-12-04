# Delete Omnichannel Agent Extension

<table><thead><tr><th width="163">HTTP Method</th><th width="350">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/omnichannel/agent/extension</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-agent-extension-association`
{% endhint %}

## Path Variables

<table><thead><tr><th width="189.33333333333331">Key</th><th width="227">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>agent5</code></td><td>The user name of the agent.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/omnichannel/agent/extension/agent5' \
--header 'X-Auth-Token: NcQtu58azANDJ1FIpJVg4GqhK9h-j61l' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```

## Example Response

```json
{
    "success": true
}
```
