# Change Room Archive State

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.changeArchivationState</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="181.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323R</code></td><td>The room ID.</td></tr><tr><td><code>action</code></td><td><code>archive</code></td><td>The room will be archived or unarchived.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.changeArchivationState' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "iu7jtPAhvEeAS5tNq",
    "action": "archive"
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
* **Invalid Room**: Occurs when the given `rid` is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "Invalid room [error-invalid-room]",
    "errorType": "error-invalid-room",
    "details": {
        "method": "unarchiveRoom"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.3.0   | Added       |
