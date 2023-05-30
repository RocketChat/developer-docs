---
description: REST API Upload Methods
---

# Upload File to a Room

Post a message with the attached file to a dedicated room.

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `/api/v1/rooms.upload/:rid` | `yes`         | `POST`      |

## Payload

| Argument      | Example                         | Required | Description                                                   |
| ------------- | ------------------------------- | -------- | ------------------------------------------------------------- |
| `file`        | `$HOME/example.txt`             | Required | A file name to upload                                         |
| `msg`         | `This is a message with a file` | Optional | A message text                                                |
| `description` | `Simple text file`              | Optional | A description of the file                                     |
| `tmid`        | `vg3h21v31v23`                  | Optional | The thread message id (if you want upload a file to a thread) |

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
For some file types, when uploading via curl you may need to set the mime type.

With some file types, curl will upload the file as `application/octet-stream`. You can pass a custom mime type like this: `-F "file=@file.wav;type=audio/wav"` to specify the type
{% endhint %}

## Example Result

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

![Message with file upload](<../../../../../../.gitbook/assets/message with file upload>)

### Error



Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Field**: Occurs when the file parameter is invalid.
* **Unknow Key**: Occurs when any extra payload is sent in the request.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
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
