# Channel Add Leader

Gives the role of Leader for a user in the current channel.

{% hint style="info" %}
It requires the `set-leader` permission.
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/channels.addLeader` | `yes`         | `POST`      |

## Payload

| Argument | Example             | Required | Description      |
| -------- | ------------------- | -------- | ---------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The channel's id |
| `userId` | `oCHkav5Zf6vmpu2W2` | Required | The user's id    |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.addLeader \
     -d '{"roomId": "ByehQjC44FwMeiLbX", "userId": "oCHkav5Zf6vmpu2W2"}'
```

## Example Result

### Success&#x20;

```javascript
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Not Allowed**: This occurs when the authenticated user doesn't have the `set-leader` permission.
* **User is already a leader**: This occurs when the user is already a leader in the channel.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Not Allowed" %}
```json
{
    "success": false,
    "error": "Not allowed [error-not-allowed]",
    "errorType": "error-not-allowed",
    "details": {
        "method": "addRoomLeader"
    }
}
```
{% endtab %}

{% tab title="User is already a leader" %}
```json
{
    "success": false,
    "error": "User is already a leader [error-user-already-leader]",
    "errorType": "error-user-already-leader"
}
```
{% endtab %}
{% endtabs %}

## Change Log

<table><thead><tr><th width="176.5">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.75.0</td><td>Added.</td></tr></tbody></table>
