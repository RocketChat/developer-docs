# Join Livechat Room

Call this endpoint to join a Livechat room.

{% hint style="info" %}
This requires the `view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/room.join</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="154">Key</th><th width="282">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>gMMeBpWyLeowCrzBv</code></td><td>Room ID that you want to join.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/room.join?roomId=gMMeBpWyLeowCrzBv' \
--header 'Content-type: application/json' \
--header 'X-Auth-Token: OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S' \
--header 'X-User-Id: f5vPj6jfkRXipkwoC' \
--data-raw ''
```
{% endcode %}

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing key**: This error is thrown when the `roomId` field is not supplied.
* **Invalid Room**: Occurs when the given `roomId` is invalid.
* **Not allowed**: Occurs when the authenticated user doesn't have permission to access the room.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing Key" %}
```json
{
    "message": "Match error: Missing key 'roomId'",
    "path": "",
    "sanitizedError": {
        "isClientSafe": true,
        "error": 400,
        "reason": "Match failed",
        "message": "Match failed [400]",
        "errorType": "Meteor.Error"
    },
    "errorType": "Match.Error",
    "success": false
}n
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```json
{
    "isClientSafe": true,
    "error": "error-invalid-room",
    "reason": "Invalid room",
    "details": {
        "method": "joinRoom"
    },
    "message": "Invalid room [error-invalid-room]",
    "errorType": "Meteor.Error",
    "success": false
}
```
{% endtab %}
{% endtabs %}
