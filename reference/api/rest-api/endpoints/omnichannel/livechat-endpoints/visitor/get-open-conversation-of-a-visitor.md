# Get Open Conversation of a Visitor

Retrieve open conversations associated with a particular visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="349">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitor/:token/room</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="206.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>8s7e9ony6ctl27e1qf8kue</code></td><td>The visitor's token.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/visitor/54fc5544030bcecda0533/room' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "rooms": [
        {
            "_id": "D2hej3mmvkwyB4HR6",
            "t": "l",
            "cl": false,
            "servedBy": {
                "_id": "XycfA5CetCPuEjqxw",
                "username": "kim.jane",
                "ts": "2021-07-18T11:50:38.822Z"
            }
        }
    ],
    "success": true
}
```
