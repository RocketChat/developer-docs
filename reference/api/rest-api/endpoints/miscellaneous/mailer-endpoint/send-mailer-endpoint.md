# Send Mailer Endpoint

Send emails to users from your workspace.

| URL              | Requires Auth | HTTP Method |
| ---------------- | ------------- | ----------- |
| `/api/v1/mailer` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Body Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>from</code></td><td><code>funke.olasupo@rocket.chat</code></td><td>Required</td><td>A valid email address to send mails from.</td></tr><tr><td><code>subject</code></td><td><code>Welcome to the Test Newsletter</code></td><td>Required</td><td>The subject of the email.</td></tr><tr><td><code>body</code></td><td>Today's newsletter is for our new users.<br>Kindly click [unsubscribe] to unsubscribe from this newsletter.</td><td>Required</td><td>The body of the email.You must use [unsubscribe] for the unsubscription link. You may use <code>[name]</code>, <code>[fname]</code>, <code>[lname]</code> for the user's full name, first name or last name, respectively. You may use [email] for the user's email.</td></tr><tr><td><code>dryrun</code></td><td><code>true</code></td><td>Required</td><td>A boolean value. If true, will only send one email to the same address as in the <code>From</code> parameter.</td></tr></tbody></table>

### Example Call <a href="#query-parameters" id="query-parameters"></a>

```json
curl --location 'http://localhost:3000/api/v1/mailer' \
--header 'x-auth-token: 1C9ajI4zUSlsefEchqaBesENo9Hw7Qa-Vh9x3VrS1iQ' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \
--data-raw '{
    "from":"funke.olasupo@rocket.chat",
    "subject":"Welcome to the Test Newsletter",
    "body":"Thank you for subscribing to the Test Newsletter. If this was not you feelfree to unsubscribe by hitting the following button [unsubscribe]"

}'
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```javascript
{
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid From Address**: The `from` parameter was be a valid email address.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Invalid From Address" %}
```javascript
{
    "success": false,
    "error": "Invalid from address [error-invalid-from-address]",
    "errorType": "error-invalid-from-address",
    "details": {
        "function": "Mailer.sendMail"
    }
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 5.4.0   | Added       |
