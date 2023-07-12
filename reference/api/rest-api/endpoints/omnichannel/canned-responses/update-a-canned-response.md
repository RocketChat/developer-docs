# Update a Canned Response

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Update a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

{% hint style="info" %}
It requires the `save-canned-responses and save-all-canned-responses` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="140">Argument</th><th width="171">Example</th><th width="109">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code></td><td><code>646ff3c3a8c3a3ba32d0fa95</code></td><td>Required</td><td>The canned response's id.</td></tr><tr><td><code>shortcut</code></td><td><code>card-declined-update</code></td><td>Required</td><td>The shortcut to the message snippet.</td></tr><tr><td><code>text</code></td><td><code>updated reasons for your card malfunction</code></td><td>Required</td><td>The message snippet</td></tr><tr><td><code>scope</code></td><td><code>department</code></td><td>Required</td><td>The scope of the canned response. It can either be <code>global</code>, <code>user</code> or <code>department</code>.</td></tr><tr><td><code>tags</code></td><td><code>["card", "failure"]</code></td><td>Optional</td><td>The tags for your canned response.</td></tr><tr><td><code>departmentId</code></td><td><code>64181a0728384134ed600dcc</code></td><td>Optional; required, only if the <code>scope</code> is <code>department</code>.</td><td>The <code>departmentId</code> where the canned response belongs to. It is required if the <code>scope</code> is <code>department</code>.</td></tr></tbody></table>

## Example payload

```javascript
{
           "_id": "646ff3c3a8c3a3ba32d0fa95",
            "shortcut": "dcard-declined-update",
            "text": "updated reasons for your card malfunction",
            "scope": "department",
            "departmentId": "64181a0728384134ed600dcc"
}
```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/canned-responses' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-wXunBXi3j77OBY-T-gl1BvJ11jYiSMt6Z_G' \
--header 'Content-Type: application/json' \
--data '{
            "_id": "646ff3c3a8c3a3ba32d0fa95",
            "shortcut": "department-check",
            "text": "This is check test for departmental canned response",
            "scope": "global",
            "departmentId": "64181a0728384134ed600dcc"
}'
```

## Example Result

### Success

```javascript
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
