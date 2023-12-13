# Disable 2FA Email

<table><thead><tr><th width="163">HTTP Method</th><th width="333">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.2fa.disableEmail</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
This endpoint requires 2FA. Refer [#call-an-endpoint-with-2fa](../../authentication-endpoints/rest-two-factor-authentication.md#call-an-endpoint-with-2fa "mention")
{% endhint %}

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/users.2fa.disableEmail\
```

## Example Response

```json
{
    "success": true
}
```
