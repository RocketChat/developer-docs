# Update an SLA

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Update an existing SLA policy.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/sla/:slaId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-sla`
{% endhint %}

## Path Parameters

<table><thead><tr><th width="152">Key</th><th width="307">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>slaId</code><mark style="color:red;"><code>*</code></mark></td><td><code>641daf3d7718f90c810429c8</code></td><td>The ID of the SLA to update.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="229">Key</th><th width="228">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Minimal updated</code></td><td>The name of the SLA policy.</td></tr><tr><td><code>description</code></td><td><code>sla description updated</code></td><td>The SLA description.</td></tr><tr><td><code>dueTimeInMinutes</code><mark style="color:red;"><code>*</code></mark></td><td><code>7</code></td><td>The SLA due time.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/sla/641daf3d7718f90c810429c8' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Minimal  updated",
    "description": "Minimal SLA updated",
    "dueTimeInMinutes": 7
}'
```
{% endcode %}

## Example Response

### Success

```json
{
    "sla": {
        "name": "Minimal updated",
        "description": "Minimal SLA updated",
        "dueTimeInMinutes": 7,
        "_updatedAt": "2023-03-24T16:31:34.712Z",
        "_id": "641daf3d7718f90c810429c8"
    },
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
```json
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
