# Send 2FA Email Code

<table><thead><tr><th width="166">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.2fa.sendEmailCode</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="166">Key</th><th width="261">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code> or <code>username</code></td><td><code>test@email.com</code></td><td>Enter the email or username.</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/users.2fa.sendEmailCode\
      -d "emailOrUsername=email@rocket.chat"
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Errors <a href="#errors" id="errors"></a>

The following error can occur.

* **Valid Email or Username**: Requires selector param for the request to be made.

{% tabs %}
{% tab title="Valid Email or Username " %}
```json
{
    "success": false,
    "error": "emailOrUsername is required [error-parameter-required]",
    "errorType": "error-parameter-required"
}
```
{% endtab %}
{% endtabs %}
