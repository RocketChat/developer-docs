# Delete a Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/units/:id</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-units`
{% endhint %}

## Path Variables

<table><thead><tr><th width="177.33333333333331">Key</th><th width="264">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>id</code><mark style="color:red;"><code>*</code></mark></td><td><code>oPK7Z735JdTuMZXmQ</code></td><td>The unit ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request DELETE 'localhost:3000/api/v1/livechat/units/oPK7Z735JdTuMZXmQ' \
--header 'x-Auth-token: jx-CrbeqbxPimsZr1UAhO3NsJdU8yB0MVoXkGOKQ3xL' \
--header 'x-user-id: 6vHSSqdBHdm2R4gfi'
```
{% endcode %}

## Example Response

```json
{
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `4.2.0` | Added       |
