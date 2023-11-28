# Get List of Monitors

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieves a list of monitors.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/monitors</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-monitors`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention")query parameters.

## Example Call

```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/monitors' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

```json
{
    "monitors": [
        {
            "_id": "gxcJTYapi5mPxuAme",
            "username": "Bruno",
            "emails": [
                {
                    "address": "",
                    "verified": false
                }
            ],
            "status": "offline",
            "name": "Bruno",
            "statusLivechat": "not-available"
        },
        {
            "_id": "QDHWqcubZunM8C4NR",
            "username": "gomes",
            "emails": [
                {
                    "address": "",
                    "verified": true
                }
            ],
            "status": "offline",
            "name": " Gomes",
            "statusLivechat": "not-available"
        },
        
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
