# Get List of Unit Monitors

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get the list of monitors associated with a specific unit.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/units/:unitId/monitors</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-monitors`
{% endhint %}

## Path Variables

<table><thead><tr><th width="211.33333333333331">Key</th><th width="253">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/monitors' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "monitors": [
        {
            "_id": "Gv8rxcv4WTEDnnGiT",
            "monitorId": "MJk4XK5QpsFWJzmSz",
            "unitId": "TGjc7wN84KxQup9cF",
            "_updatedAt": "2022-11-21T11:16:01.708Z",
            "username": "jjay"
        },
        {
            "_id": "dvSh7G6WW6J5XykQw",
            "monitorId": "GdyoCfHfd3um5N9vP",
            "unitId": "TGjc7wN84KxQup9cF",
            "_updatedAt": "2022-11-21T11:16:01.718Z",
            "username": "j.coel"
        }
    ],
    "success": true
}
```
