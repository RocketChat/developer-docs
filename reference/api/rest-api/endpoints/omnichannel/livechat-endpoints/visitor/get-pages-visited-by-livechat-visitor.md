# Get Pages Visited by Livechat Visitor

<table><thead><tr><th width="163">HTTP Method</th><th width="328">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.pagesVisited/:roomId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="212.33333333333331">Key</th><th width="247">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>hhMKhHnnbY79mGs9K</code></td><td>Livechat room ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/visitors.pagesVisited/MmGnqizEa8pvc9LRg' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

{% code overflow="wrap" %}
```json
{
    "pages": [
        {
            "_id": "6523fbf5a2f73c7460e18d60",
            "t": "livechat_navigation_history",
            "ts": "2023-10-09T13:11:17.968Z",
            "msg": "Document - https://s3.amazonaws.com/uploads.use1.cloud.rocket.cht.html%22",
            "u": {
                "_id": "rocket.cat",
                "username": "rocket.cat",
                "name": "Rocket.Cat"
            },
            "groupable": false,
            "navigation": {
                "page": {
                    "change": "url",
                    "title": "Document",
                    "location": {
                        "href": "https://s3.amazonaws.com/uploads.use1.cloud.rocket.cht.html%22"
                    }
                },
                "token": "54fc5544030bcecda053311cb6b98920bdf953f242c12"
            },
            "expireAt": 1699449077968,
            "_updatedAt": "2023-10-09T13:12:00.608Z",
            "rid": "MmGnqizEa8pvc9LRg"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
{% endcode %}
