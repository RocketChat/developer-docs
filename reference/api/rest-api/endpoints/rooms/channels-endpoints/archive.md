# Channel Archive

Archives a channel.

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/channels.archive` | `yes`         | `POST`      |

### Payload

| Argument | Example             | Required | Description      |
| -------- | ------------------- | -------- | ---------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The channel's id |

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.archive \
     -d '{ "roomId": "ByehQjC44FwMeiLbX" }'
```

### Example Result

### Success&#x20;

```javascript
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Room Archived**: This occurs when the channel is already archived.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Room Archived" %}
```json
{
    "success": false,
    "error": "The channel, add-room-websocket, is archived [error-room-archived]",
    "errorType": "error-room-archived"
}
```
{% endtab %}
{% endtabs %}

### Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
