# Get Next Agent Information

Get information about the next available agent for an incoming conversation. This endpoint returns the available agents who have not been assigned to any chat yet.

<table><thead><tr><th width="165">HTTP Method</th><th width="257">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/agent.next/:token</code></td><td><code>no</code></td></tr></tbody></table>

## Path variables

<table><thead><tr><th width="165">Key</th><th width="203">Example value</th><th>Description</th></tr></thead><tbody><tr><td><code>token </code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor <code>token</code>.</td></tr></tbody></table>

{% hint style="info" %}
To get the `token` value, call the [Get Rooms](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-room/get-rooms) endpoint to retrieve the details of all rooms.
{% endhint %}

## Example Call

{% swagger method="get" path="/api/v1/livechat/agent.next/:token" baseUrl="http://localhost:3000" summary="Get information about the next available agent" %}
{% swagger-description %}
Get next available agent information
{% endswagger-description %}

{% swagger-parameter in="path" name="token" required="true" %}
The visitor token.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```json
{
  "agent": {
    "_id": "7Gm3PoFCJWTCJ68XR",
    "emails": [
      {
        "address": "agent@rocket.chat",
        "verified": true
      }
    ],
    "name": "Livechat Agent",
    "username": "livechat.agent"
  },
  "success": true
}
```
