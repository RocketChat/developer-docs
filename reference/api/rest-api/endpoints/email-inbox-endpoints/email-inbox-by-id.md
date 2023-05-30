---
description: Gets email Inbox by id
---

# Email inbox by id

{% hint style="info" %}
Requires the user to have`manage-email-inbox`permission.
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/email-inbox/:_id` | `yes`         | `GET`       |

## Path Variable

| Argument | Example                    | Required | Description    |
| -------- | -------------------------- | -------- | -------------- |
| `_id`    | `60197e8ff82d6c83b96c53ff` | Required | Email inbox id |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/email-inbox/:_id \
```

## &#x20;Result

### Success

```javascript
{
    "_id": "60197e8ff82d6c83b96c53ff",
    "active": false,
    "name": "Rocket.Chat sample account",
    "email": "info@rocket.chat",
    "description": "",
    "senderInfo": "",
    "department": "GgYvrkAF63aeQmsh4",
    "smtp": {
        "server": "smtp.gmail.com",
        "port": 465,
        "username": "info@rocket.chat",
        "password": "kkviepoenakbccwf",
        "secure": true
    },
    "imap": {
        "server": "imap.gmail.com",
        "port": 993,
        "username": "info@rocket.chat",
        "password": "kkviepoenakbccwf",
        "secure": true
    },
    "_createdAt": "2021-02-02T16:32:15.069Z",
    "_updatedAt": "2021-09-06T17:43:49.257Z",
    "_createdBy": {
        "_id": "JxemcN9PDCdfzJeZr",
        "username": "renato.becker"
    },
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Permission**: Requires the user to have `manage-email-inbox` permission for the request to be made.
* **Not Found**: No email inbox with the matching `_id` was found.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Permission" %}
```javascript
{
    "success": false,
    "error": "error-not-allowed"
}
```
{% endtab %}

{% tab title="Not Found" %}
```javascript
{
	"success": false,
	"error": "Resource not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version     | Description |
| ----------- | ----------- |
| 3.11.0-rc.0 | Added       |
| 5.3.0 | Not Found Error Added     |
