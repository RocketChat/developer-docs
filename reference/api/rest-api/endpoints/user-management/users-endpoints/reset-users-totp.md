# Reset Users TOTP

Reset 2FA via TOTP for a user in the workspace.

{% hint style="info" %}
* It requires the edit-other-user-totp [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* It requires [two-factor authentication.](../../authentication-endpoints/rest-two-factor-authentication.md#calling-an-endpoint-with-two-factor)
{% endhint %}

<table><thead><tr><th width="166">HTTP Method</th><th width="346">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.resetTOTP</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="167.6537216828479">Key</th><th width="239">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>Q29yYlEZEByCLOQa70-QGNLRjVRhshsN2Sky6-FLAlMXbhU</code></td><td>The <code>userId</code> of the user whose TOTP you want to reset. You can also use the username.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/users.resetTOTP' \
--header 'x-auth-token: Q29yYlEZEByCLOQa70-QGNLRjVRN2Sky6-FLAlMXbhU' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s' \
--header 'x-2fa-code: 175842' \
--data '{
    "userId":"GonjPyg3gB3Z9ur9s"
}'
```

## Example Response

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have the `edit-other-user-totp` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid User**: This occurs when the `userId` or `username` in the body is invalid.
* **TOTP Required:** Requires two-factor authentication for the request to be made.
* **Invalid TOTP:** Requires a valid two-factor authentication code.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "Not allowed [error-not-allowed]",
    "errorType": "error-not-allowed"
}
```
{% endtab %}

{% tab title="Invalid User" %}
```json
{
    "success": false,
    "error": "The required \"userId\" or \"username\" param provided does not match any users [error-invalid-user]",
    "errorType": "error-invalid-user"
}
```
{% endtab %}

{% tab title="TOTP Required" %}
```json
{
    "success": false,
    "error": "TOTP Required [totp-required]",
    "errorType": "totp-required",
    "details": {
        "method": "totp",
        "codeGenerated": false,
        "availableMethods": [
            "totp"
        ]
    }
}
```
{% endtab %}

{% tab title="Invalid TOTP" %}
```json
{
    "success": false,
    "error": "TOTP Invalid [totp-invalid]",
    "errorType": "totp-invalid",
    "details": {
        "method": "totp",
        "codeGenerated": false
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.6.0   | Added       |
