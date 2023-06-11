---
description: Uploads files on livechat room.
---

# Livechat Upload

| URL                                      | Requires Auth           | HTTP Method |
| ---------------------------------------- | ----------------------- | ----------- |
| This occurs`api/v1/livechat/upload/:rid` | Yes with Visitors token | `POST`      |

## Headers

| Argument          | Example             | Required | Description           |
| ----------------- | ------------------- | -------- | --------------------- |
| `x-visitor-token` | `iNKE8a6k6cjyPyOyI` | Required | The visitor's `token` |

## Path Variables

| Argument | Example             | Required | Description                |
| -------- | ------------------- | -------- | -------------------------- |
| `rid`    | `HkHAXmXTdvZigri2X` | Required | The Omnichannel room `_id` |

## Payload

| Argument      | Example             | Required | Description             |
| ------------- | ------------------- | -------- | ----------------------- |
| `file`        | `image-file.jpg`    | Required | The file to be uploaded |
| `description` | `image description` | Optional | File description        |

## Example Payload

```javascript
{
"file": "image-file.jpg",
"descrption": "image file description"
}
```

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/livechat/upload/HkHAXmXTdvZigri2X' \
--header 'x-visitor-token: iNKE8a6k6cjyyyyyy' \
--form 'file=@"/home/rodriq/Desktop/cod.png"' \
--form 'description="image file description here"'
```

## Example Result

Returns a success true if the file was uploaded successfully.

```javascript
{
    "_id": "CeswhhAKTQMsnEbc8",
    "rid": "cbjQCtywHbuTYzmLx",
    "msg": "",
    "token": "932a1c3019aeeaa9b687bb04b979d3138458e3ab71308fac7d0e47821f76db44",
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

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **File type error**: Occurs when the file to be uploaded is of a type that has been blocked in the [upload settings](../omnichannel/omnichannel-endpoints/broken-reference/).
* **File size error**: This happens when the file to be uploaded is larger than the maximum file size set in the [upload settings](../omnichannel/omnichannel-endpoints/broken-reference/).
* **Invalid file**: This is seen when the upload fails for some reason.

{% tabs %}
{% tab title="Authorization" %}
```javascript
{
"success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="File Type" %}
```javascript
{
    "reason": "error-type-not-allowed",
    "success": false
}
```
{% endtab %}

{% tab title="File Size" %}
```javascript
{
    "reason": "error-size-not-allowed",
    "success": false
}
```
{% endtab %}

{% tab title="Invalid File" %}
```javascript
{
    "reason": "Invalid file",
    "success": false
}
```
{% endtab %}
{% endtabs %}
