# Export Room

Export room to a file or email.

{% hint style="info" %}
This requires the user to have the `mail-messages` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.export</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="200.33333333333331">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323Rf</code></td><td>The room ID.</td></tr><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>email</code> or <code>file</code></td><td>How you want the room to be exported.</td></tr><tr><td><code>dateFrom</code></td><td><code>2020-01-13</code></td><td>Start date to begin fetching.</td></tr><tr><td><code>dateTo</code></td><td><code>2021-12-13</code></td><td>End date for fetching.</td></tr><tr><td><code>format</code><mark style="color:red;"><code>*</code></mark></td><td><code>html</code> or <code>json</code></td><td>The file type to export as.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.export' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "iu7jtPAhvEeAS5tNq",
    "type": "file",
    "dateFrom": "2000-01-01",
    "dateTo": "2021-11-25",
    "format": "html"
}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Params**: Occurs when one or more needed parameters are missing.
* **Invalid Room**: Occurs when the given `rid` is invalid.
* **Not Allowed**: Occurs when the user lacks the `mail-messages` permission and doesn't have access to the room.
* **Invalid Format**: Occurs when the export format is not specified

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Params" %}
```
{
    "success": false,
    "error": "[error-invalid-params]",
    "errorType": "error-invalid-params"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "[error-invalid-room]",
    "errorType": "error-invalid-room"
}
```
{% endtab %}

{% tab title="Invalid Format" %}
```json
{
    "success": false,
    "error": "[error-invalid-format]",
    "errorType": "error-invalid-format"
}
```
{% endtab %}
{% endtabs %}

| Version | Description |
| ------- | ----------- |
| 3.8.0   | Added       |
