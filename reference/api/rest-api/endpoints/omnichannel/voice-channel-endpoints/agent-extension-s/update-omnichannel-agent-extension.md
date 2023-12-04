# Update Omnichannel Agent Extension

Update the extension associated with a specific agent.

<table><thead><tr><th width="163">HTTP Method</th><th width="345">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/omnichannel/agent/extension</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-agent-extension-association`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="180.33333333333331">Key</th><th width="222">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>2hzS2maZM39wGggdd</code></td><td>The value of the user ID or the user name.</td></tr><tr><td><code>extension</code><mark style="color:red;"><code>*</code></mark></td><td><code>700009</code></td><td>The extension number that you want to update.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request POST 'localhost:3000/api/v1/omnichannel/agent/extension' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "oWLW6v8c8oRGb4cC9",
    "extension": "70007"
}'
```
