# Get Session Information

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Retrieve session information for any session on the workspace, regardless of the session owner. This endpoint allows authorized users to access session details across the workspace.

{% hint style="info" %}
* It requires the `view-device-management`[permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* It requires [two-factor authentication.](../../authentication-endpoints/2fa.md#calling-an-endpoint-with-two-factor)
{% endhint %}

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/sessions/info.admin` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr><tr><td><code>x-2fa-code</code></td><td><code>148750Required</code></td><td>Required</td><td>The 2fa code.</td></tr></tbody></table>

## &#x20;Query Parameter

| Argument    | Example           | Required | Description     |
| ----------- | ----------------- | -------- | --------------- |
| `sessionId` | QoYYFw2t9oKks2niG | Required | The session id. |

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/sessions/info.admin?sessionId=uBNL9dTjJ4s6Pjp4K' \
--header 'X-Auth-Token: ocFlTSMfowj9tSH1vQV6ANL9SiahkKUK1KhU_PpAUtT' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'x-2fa-code: 505403'
```

## Example Result

### Success

```json
{
    "sessionId": "uBNL9dTjJ4s6Pjp4K",
    "userId": "rYhzFRd2QZjNwAAXX",
    "device": {
        "type": "browser",
        "name": "Chrome",
        "longVersion": "113.0.0.0",
        "os": {
            "name": "Windows",
            "version": "10"
        },
        "version": "113.0.0"
    },
    "host": "localhost:3000",
    "ip": "172.20.0.2",
    "loginAt": "2023-05-24T05:08:42.806Z",
    "_user": {
        "name": "Rod",
        "username": "Rod"
    },
    "_id": "uBNL9dTjJ4s6Pjp4K",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-device-management` permission.
* **TOTP Required:** Requires two-factor authentication for the request to be made.
* **Invalid TOTP:** Requires a valid two-factor authentication code.
* **Session not found:**  Occurs when the `sessionId`  does not exist.

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
```json
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
