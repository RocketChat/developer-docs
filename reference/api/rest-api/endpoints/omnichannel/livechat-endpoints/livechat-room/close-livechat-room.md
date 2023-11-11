# Close Livechat Room

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/room.close</code></td><td><code>no</code></td></tr></tbody></table>

## Body

<table><thead><tr><th width="195.33333333333331">Key</th><th width="254">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>XFzMqgn33DcsQkpJp</code></td><td>The room <code>_id</code>.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor <code>token</code>.</td></tr></tbody></table>

## Example Call

```powershell
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/room.close \
     -d '{"rid": "XFzMqgn33DcsQkpJp", 
          "token": "iNKE8a6k6cjbqWhWd"}'
```

## Example Response

```json
{
  "rid": "XFzMqgn33DcsQkpJp",
  "comment": "Closed by visitor",
  "success": true
}
```
