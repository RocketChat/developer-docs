# Get Livechat Visitor Chat History

Get the Livechat history of a visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="318">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the [#pagination](../../../../#pagination "mention")query parameters.

## Path Variables

<table><thead><tr><th width="215.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>hhMKhHnnbY79mGs9K</code></td><td>Livechat room ID.</td></tr><tr><td><code>visitorId</code><mark style="color:red;"><code>*</code></mark></td><td><code>QyBAKC5Wc8tcv6cco</code></td><td>Livechat visitor ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId \
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
            "usersCount": 1,
            "lm": "2021-07-22T17:17:04.937Z",
            "fname": "Maria",
            "t": "l",
            "ts": "2021-07-22T17:17:04.216Z",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "v": {
                "_id": "QyBAKC5Wc8tcv6cco",
                "username": "guest-537",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "status": "online",
                "lastMessageTs": "2021-07-22T17:17:04.937Z"
            },
            "cl": false,
            "open": true,
            "_updatedAt": "2021-07-22T17:17:05.078Z",
            "departmentAncestors": [
                "sriw2wmP2Zz2pPrre"
            ],
            "lastMessage": {
                "_id": "YfrxZ6gmaYLpPTxFP",
                "rid": "hhMKhHnnbY79mGs9K",
                "msg": "hi",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "alias": "Maria",
                "ts": "2021-07-22T17:17:04.937Z",
                "u": {
                    "_id": "QyBAKC5Wc8tcv6cco",
                    "username": "guest-537",
                    "name": "Maria"
                },
                "unread": true,
                "_updatedAt": "2021-07-22T17:17:05.044Z",
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
                ],
                "newRoom": false,
                "showConnecting": true
            },
            "metrics": {
                "reaction": {
                    "fd": "2021-07-22T17:17:04.449Z",
                    "ft": 0.233,
                    "tt": 0.233
                },
                "response": {
                    "avg": 0.233,
                    "fd": "2021-07-22T17:17:04.449Z",
                    "ft": 0.233,
                    "total": 1,
                    "tt": 0.233
                },
                "v": {
                    "lq": "2021-07-22T17:17:04.937Z"
                }
            },
            "waitingResponse": true
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
