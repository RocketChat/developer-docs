# Get Visitor Information

Get the details of a specific visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="341">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitor/:token</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="176">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl http://localhost:3000/api/v1/livechat/visitor/iNKE8a6k6cjbqWhWd
```
{% endcode %}

## Example Response

```json
{
  "visitor": {
    "_id": "sGtcfEYz852uguxaS",
    "username": "guest-7",
    "_updatedAt": "2018-09-21T14:10:56.529Z",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": [
      {
        "phoneNumber": "55 51 5555-5555"
      }
    ],
    "visitorEmails": [
      {
        "address": "visitor@rocket.chat"
      }
    ],
    "name": "Livechat Visitor",
    "livechatData": {
      "address": "Rocket.Chat street"
    }
  },
  "success": true
}
```
