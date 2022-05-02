---
description: Uploads files on livechat room.
---

# Upload



| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `api/v1/livechat/upload/:rid` | Yes           | `POST`      |

## Headers

| Argument          | Example             | Required | Description      |
| ----------------- | ------------------- | -------- | ---------------- |
| `x-visitor-token` | `iNKE8a6k6cjyPyOyI` | Required | Visitor `token`  |



## Path Variables

| Argument | Example              | Required | Description |
| -------- | -------------------- | -------- | ----------- |
| `rid`    | `HkHAXmXTdvZigri2X`  | Required | Room `_id`  |

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
    "success": true
}
```



### Errors

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **File type error**: Occurs when the file to be uploaded is of a type that has been blocked in the [upload settings](broken-reference).
* **File size error**: Happens when the file to be uploaded is larger than the maximum file size set in the [upload settings](broken-reference).
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

