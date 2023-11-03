# Get Visitor Information

Get the information of a specific visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="341">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.info</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="232">Key</th><th width="225.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>visitorId</code><mark style="color:red;"><code>*</code></mark></td><td><code>642fc15452492a08c3a756de</code></td><td>The visitor's id.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/visitors.info?visitorId=642fc15452492a08c3a756de' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "visitor": {
        "_id": "642fc15452492a08c3a756de",
        "username": "guest-19",
        "status": "online",
        "ts": "2023-04-07T07:08:04.375Z",
        "_updatedAt": "2023-11-03T08:23:23.449Z",
        "name": "Livechat Visitor",
        "phone": [
            {
                "phoneNumber": "55 51 5555-5555"
            }
        ],
        "token": "iNKE8a6k6cjbqWhWd",
        "visitorEmails": [
            {
                "address": "visitor@rocket.chat"
            }
        ],
        "department": "64181a0728384134ed600dcc"
    },
    "success": true
}
```
