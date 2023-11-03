---
description: Updates a Livechat message
---

# Update Livechat Message

Update a specific livechat message.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/message/:_id</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="145">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id </code><mark style="color:red;"><code>*</code></mark></td><td><code>ZKWP8LfGnRHQ3ozWa</code></td><td>The message ID that you want to update.</td></tr></tbody></table>

## Body

<table><thead><tr><th width="145">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr><tr><td><code>rid</code></td><td><code>zRAeTszXor8CCPceB</code></td><td>The room ID.</td></tr><tr><td><code>msg</code></td><td><code>editing a livechat message..</code></td><td>The updated message that you want to send.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/message/txHoTpZdqc5GaTbZ3?token=54fc5544030bcecda053311cb6b98920bdf953f242c129d7b8065000b1f9b2e9&rid=hGFwSKA28nRKut3pD' \
--header 'Content-Type: application/json' \
--data '{
    "token": "54fc5544030bcecda053311cb6b9892",
    "rid": "hGFwSKA28nRKut3pD",
    "msg": "editing livechat message.."
}'
```
{% endcode %}

## Example Response

```json
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "msg": "editing livechat message..",
    "u": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "ls": "2018-09-14T13:31:33.201Z"
  },
  "success": true
}
```
