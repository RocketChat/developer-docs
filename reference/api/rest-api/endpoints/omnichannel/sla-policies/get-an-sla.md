# Get an SLA

Get details of an SLA policy.

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-sla` or `view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/sla/:slaId</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="134">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>slaId</code></td><td><code>641daf3d7718f90c810429c8</code></td><td>Required</td><td>The Id of the SLA to fetch.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/sla/641daf3d7718f90c810429c8' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Example Result

### Success

```json
{
    "_id": "641daf3d7718f90c810429c8",
    "name": "Minimal",
    "description": "2m UI creat",
    "dueTimeInMinutes": 2,
    "_updatedAt": "2023-03-24T14:10:05.063Z",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-sla` or `view-l-room` permission.
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
