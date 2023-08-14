# Clear

Abort any import operation currently in progress. Clear any remaining data that may have been left by any previous operation.

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th>URL</th><th width="172">Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/import.clear</code></td><td><code>yes</code></td><td><code>POST</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

### Example Call

```
curl --location --request POST 'http://localhost:3000/api/v1/import.clear' \
--header 'x-auth-token: QizJozLOnWMi_2vWaLHhjfd-XYKT6XM40lTZ3zg1UMd' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json'
```

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

* **No Permission**: This occurs when the authenticated user doesn't have the  `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.3.0   | Added       |
