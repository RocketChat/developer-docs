---
description: Gets email inbox list
---

# Email inbox list

&#x20;It supports the [#pagination](../../../#pagination "mention") parameters, alongside the field parameter for [#query-and-fields](../../../#query-and-fields "mention").

{% hint style="info" %}
Requires the user to have`manage-email-inbox`permission.
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/email-inbox.list` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/email-inbox.list \
```

## Result

### Success

```javascript
{
    "emailInboxes": [
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
            }
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Permission**: Requires the user to have `manage-email-inbox` permission for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
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
{% endtabs %}

## Change Log

| Version     | Description |
| ----------- | ----------- |
| 3.11.0-rc.0 | Added       |
