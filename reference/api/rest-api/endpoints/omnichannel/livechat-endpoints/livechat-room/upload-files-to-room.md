# Upload Files to Room

Upload files to a Livechat room.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/upload/:rid</code></td><td><code>yes</code> (with visitor token)</td></tr></tbody></table>

## Headers

<table><thead><tr><th>Key</th><th width="238.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>x-visitor-token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjyPyOyI</code></td><td>The visitor token.</td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="182.33333333333331">Key</th><th width="263">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>HkHAXmXTdvZigri2X</code></td><td>The room ID.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="212.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>file</code><mark style="color:red;"><code>*</code></mark></td><td><code>image-file.jpg</code></td><td>The file to be uploaded.</td></tr><tr><td><code>description</code></td><td><code>image description</code></td><td>The file description.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request POST 'http://localhost:3000/api/v1/livechat/upload/HkHAXmXTdvZigri2X' \
--header 'x-visitor-token: iNKE8a6k6cjyyyyyy' \
    --form 'file=@"/home/rodriq/Desktop/cod.png"' \
    --form 'description="image file description here"'
```
{% endcode %}

## Example Response

### Success

```json
{
    "_id": "CeswhhAKTQMsnEbc8",
    "rid": "cbjQCtywHbuTYzmLx",
    "msg": "",
    "token": "932a1c3019aeeaa9b687bb04b979d",
    "file": {
        "_id": "uredcLri4GdehDQnD",
        "name": "globe.png",
        "type": "image/png"
    },
    "attachments": [
        {
            "ts": "1970-01-01T00:00:00.000Z",
            "title": "globe.png",
            "title_link": "/file-upload/uredcLri4GdehDQnD/globe.png",
            "title_link_download": true,
            "image_dimensions": {
                "width": 1746,
                "height": 1624
            },
            "image_preview": "/9j/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wAARCAAeACADASIAAhEBAxEB/8QAGQAAAgMBAAAAAAAAAAAAAAAABwgBBQYJ/8QAKhAAAQIFAgQHAQEAAAAAAAAAAQIDAAQFBgcREgghIjETFCNCUVJhQXH/xAAUAQEAAAAAAAAAAAAAAAAAAAAA/8QAFBEBAAAAAAAAAAAAAAAAAAAAAP/aAAwDAQACEQMRAD8AF2DMUu33PmbnypqkMq61fc/AhzrStCjWvLNsUWRbl0pGhWO5ikwtQGaRjykMNJCQpreoj3GCA5o20efIdoDJ3rZ1vXXKOMVeRbeWoaBz3D/ISzNWMJiwaqHGCp2lPn0nPr+GHvO1XPuYHHEFRWqpjKqF9A3y6fEQo/wwE8P11s3JjaRQ26PNyQ8N1GvMQVmwHmBvHeOcON79qtiVlM7S3CWlcnWSelYh4cT5HZvumoeRIuSrgT1aqBGv5AbTw9sxtAJSIEnFJdUtRMevyAWnzk90JRrz0+Yvcu5QasGSWsU9czMKHSdwCQf2EhyBetVviuOVGrulRJ9NsHpQPgQH/9k=",
            "image_url": "/file-upload/uredcLri4GdehDQnD/globe.png",
            "image_type": "image/png",
            "image_size": 562975,
            "type": "file",
            "description": "Here is the file",
            "descriptionMd": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "Here is the file"
                        }
                    ]
                }
            ]
        }
    ],
    "alias": "James",
    "ts": "2023-03-21T16:21:39.131Z",
    "u": {
        "_id": "6410766605957d866e0fcf37",
        "username": "guest-3",
        "name": "James"
    },
    "_updatedAt": "2023-03-21T16:21:39.173Z",
    "urls": [],
    "mentions": [],
    "channels": [],
    "newRoom": false,
    "showConnecting": false,
    "success": true
}
```

### Errors

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **File type error**: Occurs when the file to be uploaded is of a type that has been blocked in the upload settings.
* **File size error**: This happens when the file to be uploaded is larger than the maximum file size set in the upload settings.
* **Invalid file**: This is seen when the upload fails for some reason.

{% tabs %}
{% tab title="Authorization" %}
```json
{
"success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="File Type" %}
```json
{
    "reason": "error-type-not-allowed",
    "success": false
}
```
{% endtab %}

{% tab title="File Size" %}
```json
{
    "reason": "error-size-not-allowed",
    "success": false
}
```
{% endtab %}

{% tab title="Invalid File" %}
```json
{
    "reason": "Invalid file",
    "success": false
}
```
{% endtab %}
{% endtabs %}
