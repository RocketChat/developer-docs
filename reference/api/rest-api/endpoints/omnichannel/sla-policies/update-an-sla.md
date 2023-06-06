# Update an SLA

Update and existing SLA.

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-sla` permission.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/sla/:slaId</code></td><td><code>YES</code></td><td><code>PUT</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="134">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>slaId</code></td><td><code>641daf3d7718f90c810429c8</code></td><td>Required</td><td>The Id of the SLA to update.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="216">Argument</th><th width="188">Example</th><th width="158">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td><code>Minimal updated</code></td><td>Optional</td><td>The name of the SLA policy.</td></tr><tr><td><code>description</code></td><td><code>sla description updated</code></td><td>Optional</td><td>The SLA description.</td></tr><tr><td><code>dueTimeInMinutes</code></td><td>7</td><td>Optional</td><td>The SLA due time.</td></tr></tbody></table>

## Example Call

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

## Example Result

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
* **Not Found**: This error gets returned when no SLA is found with the Id provided.

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
