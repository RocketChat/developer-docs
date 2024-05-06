# Send User Welcome Email&#x20;

Send welcome email to a user.  It requires the `Send Emails` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

<table><thead><tr><th width="166">HTTP Method</th><th width="307">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/users.sendWelcomeEmail</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument                                      | Example          | Description                                                 |
| --------------------------------------------- | ---------------- | ----------------------------------------------------------- |
| `email`` `<mark style="color:red;">`*`</mark> | test@example.com | The email address of the user to send the welcome email to. |

## Example Call

```bash
curl --location --request POST http://localhost:3000/api/v1/users.sendWelcomeEmail\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name' \
--data-raw '{
    "email":"test@email.com"
}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **SMPT not configured**:  SMTP is not properly configured on your workspace

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="SMPT not configured" %}
```json
{
    "success": false,
    "error": "SMTP is not configured [error-email-send-failed]",
    "errorType": "error-email-send-failed",
    "details": {
        "method": "sendWelcomeEmail"
    }
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 6.8.0   | Added       |
