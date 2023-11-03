# Delete Livechat Message

Remove a specific livechat message.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/message/:_id</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="163">Key</th><th width="255">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>ZKWP8LfGnRHQ3ozWa</code></td><td>The message ID.</td></tr></tbody></table>

## Body

<table><thead><tr><th width="163">Key</th><th width="255">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>54fc5544030b</code></td><td>The visitor token.</td></tr><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>hGFwSKA28nRKut3pD</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/livechat/message/mz6TKjsvZiausYjev' \
--header 'Content-Type: application/json' \
--data '{
    "token": "54fc5544030bcecda053311cb6b989",
    "rid": "hGFwSKA28nRKut3pD"
}'
```
{% endcode %}

## Example Response

```json
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "ls": "2018-09-14T13:31:33.279Z"
  },
  "success": true
}
```
