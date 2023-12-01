# Create SLA Policy

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/livechat/sla</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-sla`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="234">Key</th><th width="207">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>grand</code></td><td>The name of the SLA policy.</td></tr><tr><td><code>description</code><mark style="color:red;"><code>*</code></mark></td><td><code>sla description</code></td><td>The SLA description.</td></tr><tr><td><code>dueTimeInMinutes</code><mark style="color:red;"><code>*</code></mark></td><td><code>4</code></td><td>The SLA due time.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/sla' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Optimum",
    "description": "OPtimum SLA",
    "dueTimeInMinutes": 4
}'
```

## Example Response

### Success

```json
{
    "sla": {
        "name": "Optimum",
        "description": "Optimum SLA",
        "dueTimeInMinutes": 4,
        "_id": "641db89a7718f90c810429cc"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have  `manage-livechat-sla` permission.
* **Invalid Parameter**: Occurs when a required parameter is not passed.
* **Duplicate**: When an SLA is created having the same `name` or `dueTimeInMinutes` as an existing SLA.

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

{% tab title="Invalid Parameter" %}
```
{
    "success": false,
    "error": "must have required property 'name' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}

{% tab title="Duplicate" %}
```
{
    "success": false,
    "error": "error-duplicated-sla"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
