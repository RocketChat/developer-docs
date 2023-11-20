# Search Visitor Chat

Get the Livechat information of a visitor. This endpoint returns only those chats that are served and closed.

<table><thead><tr><th width="163">HTTP Method</th><th width="318">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="230.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>hhMKhHnnbY79mGs9K</code></td><td>Livechat room ID.</td></tr><tr><td><code>visitorId</code><mark style="color:red;"><code>*</code></mark></td><td><code>QyBAKC5Wc8tcv6cco</code></td><td>Livechat visitor ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "history": [
        {
            "_id": "hhMKhHnnbY79mGs9K",
            "msgs": 2,
            "fname": "Maria",
            "ts": "2021-07-22T17:17:04.216Z",
            "v": {
                "_id": "QyBAKC5Wc8tcv6cco",
                "username": "guest-537",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "status": "online",
                "lastMessageTs": "2021-07-22T17:17:04.937Z"
            }
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
