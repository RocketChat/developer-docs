# Archive Channel

Archives a channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.archive</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="230.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID that you want to archive.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.archive \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX" }'
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
