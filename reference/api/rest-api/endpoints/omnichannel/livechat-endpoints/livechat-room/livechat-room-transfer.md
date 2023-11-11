# Transfer Livechat Room

Transfer an omnichannel conversation to another department.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/room.transfer</code></td><td><code>no</code></td></tr></tbody></table>

## Payload

<table><thead><tr><th width="215.33333333333331">Key</th><th width="232">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>XFzMqgn33DcsQkpJp</code></td><td>The room <code>_id</code>.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor <code>token</code>.</td></tr><tr><td><code>department</code><mark style="color:red;"><code>*</code></mark></td><td><code>wXpPLofkffqWAwDNF</code></td><td>The new <code>department</code>. To get the department ID, call the <a href="../livechat-config.md">Get Livechat Configurations</a> endpoint. Note that the endpoint only returns public departments.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/room.transfer \
     -d '{"rid": "XFzMqgn33DcsQkpJp", 
          "token": "iNKE8a6k6cjbqWhWd", 
          "department": "wXpPLofkffqWAwDNF"}'
```
{% endcode %}

## Example Response

```json
{
  "room": {
    "_id": "XFzMqgn33DcsQkpJp",
    "servedBy": {
      "_id": "wiyTfFKXr5GhgRu9A",
      "username": "livechat.agent"
    },
    "open": true,
    "departmentId": "wXpPLofkffqWAwDNF"
  },
  "success": true
}
```
