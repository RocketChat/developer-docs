# Search Visitors by Term

Search Livechat visitors using a specific term.

<table><thead><tr><th width="163">HTTP Method</th><th width="351">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.search</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention")query parameters and the additional required parameter as follows:

<table><thead><tr><th width="218.33333333333331">Key</th><th width="210">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>term</code><mark style="color:red;"><code>*</code></mark></td><td><code>James</code></td><td>The visitor's name, username, email, or phone.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/visitors.search?term=James' \
--header 'X-Auth-Token: EZmA1YMbEfghEPOmc03k0R9QiuVvKWjQClKVoF8x7LY' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Example Response

```json
{
    "visitors": [
        {
            "_id": "6410749f28384134ed600ce4",
            "username": "guest-14",
            "name": "James",
            "visitorEmails": [
                {
                    "address": "pilebe6631@kaudat.com"
                }
            ],
            "lastChat": {
                "_id": "eJ5ZzeT2XkLtcBkMM",
                "ts": "2023-03-14T13:21:02.239Z"
            }
        },
        {
            "_id": "63db8d4990fe6eda42ad429a",
            "username": "guest-3",
            "name": "James",
            "visitorEmails": [
                {
                    "address": "f.r@rocket.chat"
                }
            ],
            "lastChat": {
                "_id": "82htiMFZLCtvRFqZi",
                "ts": "2023-02-06T12:34:53.392Z"
            }
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
