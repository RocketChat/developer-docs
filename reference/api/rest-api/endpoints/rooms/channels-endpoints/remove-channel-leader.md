# Remove Channel Leader

Removes the role of `leader` for a user in the current channel.

{% hint style="info" %}
It requires the `set-leader` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.removeLeader</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="191.33333333333331">Key</th><th width="238">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>oCHkav5Zf6vmpu2W2</code></td><td>The user ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.removeLeader \
     -d '{
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "oCHkav5Zf6vmpu2W2"}'
```

## Example Response

### Success&#x20;

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Not Allowed**: This occurs when the authenticated user doesn't have the `set-leader` permission.
* **User is not a leader**: This occurs when the user is not a leader in the channel.

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
        "method": "removeRoomLeader"
    }
}
```
{% endtab %}

{% tab title="User is already a leader" %}
```json
{
    "success": false,
    "error": "User is not a leader [error-user-not-leader]",
    "errorType": "error-user-not-leader"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.75.0  | Added.      |
