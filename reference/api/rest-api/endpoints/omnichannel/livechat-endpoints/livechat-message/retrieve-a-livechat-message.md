# Get a Livechat Message

Retrieve specific livechat message information.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/message/:_id</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="186.33333333333331">Key</th><th width="249">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>AgRFdj96mbHDPrTHq</code></td><td>The message ID.</td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="163">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>8s7e9ony6ctl27e1qf8kue</code></td><td>The visitor token.</td></tr><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>mmqCzYgiL8fzRYfuY</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/message/txHoTpZdqc5GaTbZ3?token=54fc5544030bcecda053311cb6b98920bdf953f242c1' \
```
{% endcode %}

## Example Response

```javascript
{
    "message": {
        "_id": "AgRFdj96mbHDPrTHq",
        "rid": "mmqCzYgiL8fzRYfuY",
        "msg": "hi",
        "token": "8s7e9ony6ctl27e1qf8kue",
        "alias": "Mary",
        "ts": "2021-07-13T16:20:26.672Z",
        "u": {
            "_id": "47Dajwh9DjpnTAugW",
            "username": "guest-165",
            "name": "Mary"
        },
        "unread": true,
        "_updatedAt": "2021-07-13T16:20:26.776Z",
        "urls": [],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "hi"
                    }
                ]
            }
        ]
    },
    "success": true
}
```
