# Download Public Import File

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/downloadPublicImportFile` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="164">Argument</th><th width="137">Example</th><th width="100">Required</th><th>Description</th></tr></thead><tbody><tr><td>fileUrl</td><td><code>https://www.freepik.com/photos/dog</code></td><td>Required</td><td>The url of the file. It must start with <code>http</code> or <code>https</code>.</td></tr><tr><td>importerKey</td><td><code>pending-avatars</code></td><td>Required</td><td>It indicates how Rocket.Chat should handle the uploaded file. The accepted importer keys are: <code>csv</code>, <code>hipchatenterprise</code>, <code>pending-avatars</code>, <code>pending-files</code>, <code>slack</code> and <code>slack-users</code></td></tr></tbody></table>

## Example payload

```javascript
{
    "fileUrl":"https://www.freepik.com/photos/dog",
    "importerKey":"pending-avatars"
 
}
```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/downloadPublicImportFile' \
--header 'x-auth-token: DTRPbgzQ0EDlTE3sdd3Nt7WfaWZE-lG1ayi9Pfa28Fm' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s' \
--header 'Content-Type: application/json' \
--data '{
    "fileUrl":"https://www.freepik.com/photos/dog",
    "importerKey":"pending-avatars"
 
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

* **Invalid Importer Key:** This happens when the importer key does not match any of the accepted options.
* **No Permission**: This occurs when the authenticated user doesn't have the  `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Import File Missing:** It occurs when the `fileUrl` for the image does not start with `http`.

{% tabs %}
{% tab title="Invalid Importer Key" %}
```
{
    "success": false,
    "error": "The importer (png) has no import class defined. [error-importer-not-defined]",
    "errorType": "error-importer-not-defined",
    "details": "uploadImportFile"
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

{% tab title="Import File Missing" %}
```json
{
    "success": false,
    "error": "htt://www.freepik.com/photos/dog [error-import-file-missing]",
    "errorType": "error-import-file-missing",
    "details": "downloadPublicImportFile"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `3.0.0` | Added       |
