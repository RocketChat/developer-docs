# Create a Canned Response

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Create a new [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/canned-responses</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `save-canned-responses`
* `save-all-canned-responses`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="175">Key</th><th width="211">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>shortcut</code><mark style="color:red;"><code>*</code></mark></td><td><code>card-declined</code></td><td>The shortcut to trigger the message snippet.</td></tr><tr><td><code>text</code><mark style="color:red;"><code>*</code></mark></td><td><code>reasons for your card malfunction</code></td><td>The message snippet.</td></tr><tr><td><code>scope</code><mark style="color:red;"><code>*</code></mark></td><td><code>global</code></td><td>The scope of the canned response. It can either be <code>global</code>, <code>user</code> or <code>department</code>.</td></tr><tr><td><code>tags</code></td><td><code>card</code></td><td>The tags for your canned response.</td></tr><tr><td><code>departmentId</code></td><td><code>64181a0728384134ed600dcc</code></td><td>The <code>departmentId</code> where the canned response belongs to. It is required if the <code>scope</code> is <code>department</code>.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/canned-responses' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-wXunBXi3j77OBY-T-gl1BvJ11jYiSMt6Z_G' \
--header 'Content-Type: application/json' \
--data '{
    "shortcut": "test-canned",
    "text": "This is an example test for canned response",
    "scope": "global",
    "tags": ["tag1", "tag2"]
}'
```

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
* **No Permission**: Occurs when the authenticated user doesn't have the  `save-canned-responses`  and `save-all-canned-responses`  [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid Department**: If the `scope` of the canned response is `department`, a  valid `departmentId` is required to specify the department it belongs to. This error occurs when there is no valid `departmentId` in the body of the request.
* **Shortcut Exists:** The `shortcut` value of the canned response must be unique. This error occurs when the shortcut already exists.

{% tabs %}
{% tab title="Authorization" %}
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
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Invalid Department" %}
```json
{
    "success": false,
    "error": "Invalid department [error-invalid-department]",
    "errorType": "error-invalid-department",
    "details": {
        "method": "saveCannedResponse"
    }
}
```
{% endtab %}

{% tab title="Shortcut Exists" %}
```json
{
    "success": false,
    "error": "Shortcut provided already exists [error-invalid-shortcut]",
    "errorType": "error-invalid-shortcut",
    "details": {
        "method": "saveCannedResponse"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
