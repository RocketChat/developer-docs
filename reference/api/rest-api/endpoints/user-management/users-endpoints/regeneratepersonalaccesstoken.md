# Regenerate Personal Access Token

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.regeneratePersonalAccessToken</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* Permission required: `create-personal-access-tokens`
* This endpoint required 2FA. Refer to [#call-an-endpoint-with-2fa](../../authentication-endpoints/rest-two-factor-authentication.md#call-an-endpoint-with-2fa "mention")
{% endhint %}

## Body Parameters

<table><thead><tr><th width="235">Key</th><th width="206.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>tokenName</code><mark style="color:red;"><code>*</code></mark></td><td><code>mypersonaltoken</code></td><td>The name of the token.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.regeneratePersonalAccessToken \
     -d '{ 
          "tokenName": "mypersonaltoken" }'
```

## Example Response

```json
{
    "token": "sSfSoNW8Pb7S8BHEz3uJXYRM3__ML9GxPY1PxGzqAcn",
    "success": true
}
```

## Change Log

<table><thead><tr><th width="326">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.69.0</td><td>Added</td></tr></tbody></table>
