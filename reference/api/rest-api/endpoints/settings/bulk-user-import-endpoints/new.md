# New

Creates a new import operation; If an operation was already running, it will be aborted. Any data from previous imports will be cleared automatically.

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `/api/v1/import.new` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

### Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/import.new' \
--header 'x-auth-token: QizJozLOnWMi_2vWaLHhjfd-XYKT6XM40lTZ3zg1UMd' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \
--data ''
```

## Example Result

### Success

```javascript
{
    "operation": {
        "_id": "64d69545ee8ae821983005f5",
        "type": "api",
        "importerKey": "api",
        "ts": "2023-08-11T20:08:37.655Z",
        "status": "importer_new",
        "valid": true,
        "user": "rbAXPnMktTFbNpwtJ",
        "_updatedAt": "2023-08-11T20:08:37.655Z"
    },
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
| `6.3.0` | Added       |
