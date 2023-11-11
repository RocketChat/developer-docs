# Forward Livechat Room

The Chatbot agent forwards the chat to a human agent.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/room.forward</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body

<table><thead><tr><th width="202.33333333333331">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>XFzMqgn33DcsQkpJp</code></td><td>The room <code>_id</code>.</td></tr><tr><td><code>userId</code></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The new <code>agent ID</code>.</td></tr><tr><td><code>departmentId</code></td><td><code>wXpPLofkffqWAwDNF</code></td><td>The new <code>department ID</code>.</td></tr></tbody></table>

## Example Call

With `roomId` and `userId`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/room.forward \
     -d '{"roomId": "XFzMqgn33DcsQkpJp", 
          "userId": "iNKE8a6k6cjbqWhWd"}'
```

With `roomId` and `departmentId`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/room.forward \
     -d '{"roomId": "XFzMqgn33DcsQkpJp", 
          "departmentId": "wXpPLofkffqWAwDNF"}'
```

## Example Response

```javascript
{
  "success": true
}
```
