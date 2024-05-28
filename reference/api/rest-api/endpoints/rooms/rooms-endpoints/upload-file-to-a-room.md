# Upload File to a Room

Post a message with the attached file to a dedicated room.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.upload/:rid</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="203.33333333333331">Key</th><th width="241">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>hdsjjd783hkd</code></td><td>The room ID to which you want to upload the file.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="205.33333333333331">Key</th><th width="258">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>file</code><mark style="color:red;"><code>*</code></mark></td><td><code>$HOME/example.txt</code></td><td>A file name to upload.</td></tr><tr><td><code>msg</code></td><td><code>This is a message with a file</code></td><td>A message text.</td></tr><tr><td><code>description</code></td><td><code>Simple text file</code></td><td>A description of the file.</td></tr><tr><td><code>tmid</code></td><td><code>vg3h21v31v23</code></td><td>The thread message id (if you want upload a file to a thread).</td></tr><tr><td><code>customFields</code></td><td><code>{"priority": "high"}</code></td><td>You can add custom fields for messages. For example, set priorities for messages.<br><br>You must enable this option and define the validation in the workspace settings. See the <a href="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/message">Message</a> settings for further information.</td></tr></tbody></table>

## Example Call

```bash
curl "http://localhost:3000/api/v1/rooms.upload/GENERAL" \
    -F file=@$HOME/example.txt \
    -F "msg=This is a message with a file" \
    -F "description=Simple text file" \
    -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
    -H "X-User-Id: hw5DThnhQmxDWnavu"
```

{% hint style="info" %}
For some file types, when uploading via curl, you may need to set the mime type.

With some file types, curl will upload the file as `application/octet-stream`. You can pass a custom mime type like this: `-F "file=@file.wav;type=audio/wav"` to specify the type.
{% endhint %}

## Example Response

### Success

```json
{
    "message": {
        "_id": "XhqGxkXYtcYba2F9K",
        "rid": "GENERAL",
        "ts": "2022-06-29T07:34:33.736Z",
        "msg": "This is a message with a file",
        "file": {
            "_id": "pw6oyrjBStWwMdeMv",
            "name": "example.txt",
            "type": "text/plain"
        },
        "files": [
            {
                "_id": "pw6oyrjBStWwMdeMv",
                "name": "example.txt",
                "type": "text/plain"
            }
        ],
        "attachments": [
            {
                "ts": "1970-01-01T00:00:00.000Z",
                "title": "example.txt",
                "title_link": "/file-upload/pw6oyrjBStWwMdeMv/example.txt",
                "title_link_download": true,
                "type": "file",
                "description": "Simple text file"
            }
        ],
        "u": {
            "_id": "g8aroJivN5R32TxCm",
            "username": "rodriq",
            "name": "Rodriq"
        },
        "_updatedAt": "2022-06-29T07:34:33.811Z",
        "urls": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "This is a message with a file"
                    }
                ]
            }
        ]
    },
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Field**: Occurs when the file parameter is invalid.
* **Unknow Key**: Occurs when any extra payload is sent in the request.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Field" %}
```json
{
    "success": false,
    "error": "[invalid-field]",
    "errorType": "invalid-field"
}
```
{% endtab %}

{% tab title="Unknown Key" %}
```json
{
    "success": false,
    "error": "Match error: Unknown key in field dasd"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description                          |
| ------- | ------------------------------------ |
| 1.0.0   | Return Message object on file upload |
| 0.62.0  | Added                                |
