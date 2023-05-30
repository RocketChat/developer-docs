# Logout Session

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

This endpoint allows an authenticated user{ "success": false, "error": "User does not have the permissions required for this action \[error-unauthorized]" }{ "success": false, "error": "User does not have the permissions required for this action \[error-unauthorized]" } to log out any user's session on the workspace. It provides the capability to terminate sessions of other users, ensuring workspace security and management.

{% hint style="info" %}
* It requires the`logout-device-management` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* It requires [two-factor authentication.](../../2fa.md#calling-an-endpoint-with-two-factor)
{% endhint %}

| URL                       | Requires Auth | HTTP Method |
| ------------------------- | ------------- | ----------- |
| `/api/v1/sessions/logout` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr><tr><td><code>x-2fa-code</code></td><td><code>148750</code></td><td>Required</td><td>The 2fa code.</td></tr></tbody></table>

## Payload

| Argument    | Example             | Required | Description     |
| ----------- | ------------------- | -------- | --------------- |
| `sessionId` | `WJ2giBwm4B9mcojFi` | Required | The session id. |

## Example Payload

```javascript
{
    "sessionId":"tTouumJMrHMjnedWf"
}
```

## Example Call

<pre class="language-javascript"><code class="lang-javascript">curl --location 'http://localhost:3000/api/v1/sessions/logout' \
--header 'Content-Type: application/json' \
--header 'X-Auth-Token: ocFlTSMfowj9tSH1vQV6ANL9SiahkKUK1KhU_PpAUtT' \
<strong>--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
</strong>--header 'x-2fa-code: 505403' \
--data '{
    "sessionId":"tTouumJMrHMjnedWf"
}'
</code></pre>

## Example Result

### Success

```json
{
    "sessionId": "tTouumJMrHMjnedWf",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `logout-device-management` permission.
* **TOTP Required:** Requires two-factor authentication for the request to be made.
* **Invalid TOTP:** Requires a valid two-factor authentication code.
* **Session not found:**  Occurs when the `sessionId` does not exist.

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
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Session not found" %}
```
{
    "success": false,
    "error": "Session not found"
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
| 5.0.0   | Added       |
