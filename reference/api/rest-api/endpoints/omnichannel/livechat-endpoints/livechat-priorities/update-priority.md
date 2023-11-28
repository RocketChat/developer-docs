# Update Priority

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Update an existing priority.

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="362">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/priorities/:priorityId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="205">Key</th><th width="277">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>priorityId</code><mark style="color:red;"><code>*</code></mark></td><td><code>641daf3d7718f90c810429c8</code></td><td>The ID of the priority to update.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="195">Key</th><th width="211">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Very low</code></td><td>The name of the priority.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/priorities/64007cc2fa0ed7dd905092e3' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Very low"
}'
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
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` permission.
* **Unable to Update**: This error gets returned when no Priority is found with the Id provided.
* **Duplicate**: Occurs when the priority to be updated will cause a duplicate.

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

{% tab title="Unable to Update" %}
```json
{
    "success": false,
    "error": "error-unable-to-update-priority"
}
```
{% endtab %}

{% tab title="Duplicate" %}
```json
{
    "success": false,
    "error": "error-duplicate-priority-name"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
