# LDAP Sync

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Syncs your [LDAP data](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/ldap) based on the[ data sync configurations](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/ldap/ldap-data-sync-settings).

{% hint style="info" %}
* It requires the `sync-auth-services-users` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* It requires [two-factor authentication.](../../authentication-endpoints/rest-two-factor-authentication.md#calling-an-endpoint-with-two-factor)
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="268">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/ldap.syncNow</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/ldap.syncNow' \
--header 'x-auth-token: 0ueGH0dyW5ewtemsyiBlrC8pU4yBbRUtReXiglvisoZ' \
--header 'x-user-id: 2tTEqR7ZNMJ4HGGNa' \
--header 'x-2fa-code: 773917'
```

## Example Response

### Success

```json
{
    "message": "Sync_in_progress",
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have the `sync-auth-services-users` permission.
* **LDAP Disabled**: This occurs when the [LDAP connection](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/ldap/ldap-connection-setting) is disabled.
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
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="LDAP Disabled" %}
```json
{
    "success": false,
    "error": "LDAP_disabled"
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

<table><thead><tr><th width="358">Version</th><th>Description</th></tr></thead><tbody><tr><td>4.0.0</td><td>Added</td></tr><tr><td>5.2.0</td><td>Include <code>syncAvatars</code> on <code>ldap.syncNow</code></td></tr></tbody></table>
