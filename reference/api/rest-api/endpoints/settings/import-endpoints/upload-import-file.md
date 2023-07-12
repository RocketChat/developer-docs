# Upload Import File

This endpoint takes in the binary content of the imported file, along with additional information about its content, and stores it in a buffer.

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/uploadImportFile` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="164">Argument</th><th width="137">Example</th><th width="100">Required</th><th>Description</th></tr></thead><tbody><tr><td>binaryContent</td><td><code>/test.csv</code></td><td>Required</td><td>The uploaded file.</td></tr><tr><td>contentType</td><td><code>text/csv</code></td><td>Required</td><td>The imported file <a href="upload-import-file.md#headers">MIME </a><a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types">type</a>.</td></tr><tr><td>fileName</td><td><code>Testfile</code></td><td>Required</td><td>The name of the file to be imported.</td></tr><tr><td>importerKey</td><td><code>csv</code></td><td>Required</td><td>It indicates how Rocket.Chat should handle the uploaded file. The accepted importer keys are: <code>csv</code>, <code>hipchatenterprise</code>, <code>pending-avatars</code>, <code>pending-files</code>, <code>slack</code> and <code>slack-users</code></td></tr></tbody></table>

## Example payload

```javascript
{
    "binaryContent":"/testfile.csv",
    "importerKey":"csv",
    "fileName":"Testfile",
    "contentType":"text/csv"
}

```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/uploadImportFile' \
--header 'x-auth-token: DTRPbgzQ0EDlTE3sdd3Nt7WfaWZE-lG1ayi9Pfa28Fm' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s' \
--header 'Content-Type: application/json' \
--data '{
    "binaryContent":"/fole/hola",
    "importerKey":"csv",
    "fileName":"Tryout.csv",
    "contentType":"text/csv"
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

{% tabs %}
{% tab title="Invalid Importer Key" %}
```json
{
    "success": false,
    "error": "The importer (png) has no import class defined. [error-importer-not-defined]",
    "errorType": "error-importer-not-defined",
    "details": "uploadImportFile"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `3.0.0` | Added       |
