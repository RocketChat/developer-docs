# Test LDAP User Search

Test if a given username can be found in the LDAP server using the authentication and filter settings provided to Rocket.Chat.

<table><thead><tr><th width="163">HTTP Method</th><th width="308">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/ldap.testSearch</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* Permission required: `test-admin-options`
* Make sure that LDAP is enabled on your workspace.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="210">Key</th><th width="205">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>bob</code></td><td>The username that you want to search.</td></tr></tbody></table>

## Example Call

```bash
curl 'http://localhost:3000/api/v1/ldap.testSearch' \
  -H 'X-Auth-Token: yC3dGLAQVdge_utGjB57tgDEAgFhQewFTRa2Tx6GEsI' \
  -H 'X-User-Id: hig6ucyFZ9bamdKgG' \
  --data-raw '{
    "username":"test.user"}'
```

## Example Response

User found:

```json
{
  "message": "LDAP_User_Found",
  "success": true
}
```

User not found:

```json
{
  "success": false,
  "error": "User not found"
}
```
