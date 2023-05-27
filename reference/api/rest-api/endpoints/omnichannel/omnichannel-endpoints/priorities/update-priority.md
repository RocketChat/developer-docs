# Update Priority

Update an existing Priority.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` permission.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>livechat/priorities/:priorityId</code></td><td><code>YES</code></td><td><code>PUT</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated ouser ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="152">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>priorityId</code></td><td><code>641daf3d7718f90c810429c8</code></td><td>Required</td><td>The Id of the Priority to update.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="216">Argument</th><th width="188">Example</th><th width="158">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td><code>Very low</code></td><td>Optional</td><td>The name of the Priority.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/priorities/64007cc2fa0ed7dd905092e3' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Very low"
}'
```

## Example Result

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
