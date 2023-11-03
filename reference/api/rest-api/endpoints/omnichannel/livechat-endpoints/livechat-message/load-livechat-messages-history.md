# Get Livechat Message History

Get the entire message history of a conversation.

<table><thead><tr><th width="163">HTTP Method</th><th width="295">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/messages.history/:rid</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="191.33333333333331">Key</th><th width="245">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid </code><mark style="color:red;"><code>*</code></mark></td><td><code>KuACMJ5MpN6SfAFWg</code></td><td>The room ID.</td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="160">Key</th><th width="223">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token </code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr><tr><td><code>ls</code></td><td><code>2018-09-14T13:31:33.201Z</code></td><td>The timestamp to start loading the messages.</td></tr><tr><td><code>end</code></td><td><code>2018-09-14T14:31:33.201Z</code></td><td>The timestamp limit to stop loading the messages.</td></tr><tr><td><code>limit</code></td><td><code>25</code></td><td>The number of messages to load.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/message/txHoTpZdqc5GaTbZ3?token=54fc5544030bcecda053311cb6b98920bdf' \
```
{% endcode %}

## Example Response

```json
{
  "messages": [{
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "rid": "KuACMJ5MpN6SfAFWg",
    "msg": "editing livechat message..",
    "token": "iNKE8a6k6cjbqWhWd",
    "alias": "Livechat Visitor",
    "ls": "2018-09-14T13:31:33.201Z",
    "u": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "mentions": [],
    "channels": [],
    "_updatedAt": "2018-09-14T13:31:33.222Z",
    "editedAt": "2018-09-14T13:31:33.219Z",
    "editedBy": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4"
    },
    "urls": []
  }],
  "unreadNotLoaded": 0,
  "success": true
}
```
