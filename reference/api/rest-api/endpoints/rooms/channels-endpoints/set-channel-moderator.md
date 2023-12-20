# Set Channel Moderator

Gives the role of `moderator` to a user in the current channel.

{% hint style="info" %}
It requires the `set-moderator` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.addModerator</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="171">Key</th><th width="265">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID for which you want to set the moderator.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>nSYqWzZ4GsKTX4dyK</code></td><td>The user ID that you want to set as the moderator.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.addModerator \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "nSYqWzZ4GsKTX4dyK" }'
```

## Example Response

### Success&#x20;

```javascript
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Not Allowed**: This occurs when the authenticated user doesn't have the `set-moderator` permission.
* **User is already a moderator**: This occurs when the user is already a moderator in the channel.

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
        "method": "addRoomModerator"
    }
}
```
{% endtab %}

{% tab title="User is already a moderator" %}
```json
{
    "success": false,
    "error": "User is already a moderator [error-user-already-moderator]",
    "errorType": "error-user-already-moderator"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.49.4  | Added       |
