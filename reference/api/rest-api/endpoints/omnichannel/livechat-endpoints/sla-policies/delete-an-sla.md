# Delete an SLA

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/sla/:slaId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-sla`
{% endhint %}

## Path Parameters

<table><thead><tr><th width="152">Key</th><th width="307">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>slaId</code><mark style="color:red;"><code>*</code></mark></td><td><code>641daf3d7718f90c810429c8</code></td><td>The ID of the SLA to delete.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/livechat/sla/641daf3d7718f90c810429c8' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```
{% endcode %}

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-sla` permission.
* **Not Found**: This error gets returned when no SLA is found with the ID provided.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```
{
    "success": false,
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="Not Found" %}
```json
{
    "success": false,
    "error": "SLA with id gfgfg56g429c8 not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
