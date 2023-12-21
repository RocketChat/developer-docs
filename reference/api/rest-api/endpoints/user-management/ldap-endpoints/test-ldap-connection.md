# Test LDAP Connection

Test if Rocket.Chat can connect to the specified LDAP server using the port and host provided in the Rocket.Chat settings.

<table><thead><tr><th width="163">HTTP Method</th><th width="308">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/ldap.testConnection</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* Permission required: `test-admin-options`
* Make sure that LDAP is enabled on your workspace.
{% endhint %}

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/ldap.testConnection' \
--header 'X-Auth-Token: x65a7F7aZZtW_H2hTgKEsp_RGNqvoyF' \
--header 'X-User-Id: CkCPNcvfmWLqC'
```

## Example Response

```json
{
    "message": "Connection_success",
    "success": true
}
```

```json
{
    "message": "Connection_failed",
    "success": false
}
```
