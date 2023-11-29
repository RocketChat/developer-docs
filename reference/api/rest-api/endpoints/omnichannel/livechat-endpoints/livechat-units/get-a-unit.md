# Get a Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get details of a specific unit.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/units/:unitId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-units`
{% endhint %}

## Path Variables

<table><thead><tr><th width="190.33333333333331">Key</th><th width="268">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/sriw2wmP2Zz2pPrre \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "_id": "LnM2rzbknjYSkkd5p",
    "name": "Sales Unit",
    "visibility": "public",
    "type": "u",
    "numMonitors": 1,
    "numDepartments": 2,
    "_updatedAt": "2022-09-15T11:44:15.721Z",
    "success": true
}
```
