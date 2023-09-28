# Channel Remove Moderator

Removes the role of moderator from a user in the current channel.

{% hint style="info" %}
It requires the `set-moderator`[permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/channels.removeModerator` | `yes`         | `POST`      |

## Payload

| Argument | Example             | Required | Description      |
| -------- | ------------------- | -------- | ---------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The channel's id |
| `userId` | `nSYqWzZ4GsKTX4dyK` | Required | The user's id    |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.removeModerator \
     -d '{ "roomId": "ByehQjC44FwMeiLbX", "userId": "nSYqWzZ4GsKTX4dyK" }'
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
* **Not Allowed**: This occurs when the authenticated user doesn't have the `set-moderator` permission.
* **User is not a moderator**: This occurs when the user is not a moderator in the channel.

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
        "method": "removeRoomModerator"
    }
}
```
{% endtab %}

{% tab title="User is not a moderator" %}
```json
{
    "success": false,
    "error": "User is not a moderator [error-user-not-moderator]",
    "errorType": "error-user-not-moderator",
    "details": {
        "method": "removeRoomModerator"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.49.4  | Added       |
