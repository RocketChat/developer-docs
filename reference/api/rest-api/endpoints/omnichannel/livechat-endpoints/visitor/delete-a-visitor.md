# Delete Visitor

Delete a specific visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="354">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/visitor/:token</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="204.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>8s7e9ony6ctl27e1qf8kue</code></td><td>The visitor <code>token</code>.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/livechat/visitor/iNKE8a6k6cjbqWhWd' \
```
{% endcode %}

## Example Result

```javascript
{
    "visitor": {
        "_id": "47Dajwh9DjpnTAugW",
        "ts": "2021-07-18T13:28:38.962Z"
    },
    "success": true
}
```
