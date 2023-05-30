---
description: Sets the email inbox for your server.
---

# Set email inbox

{% hint style="info" %}
Requires the user to have`manage-email-inbox`permission.
{% endhint %}

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `/api/v1/email-inbox` | `yes`         | `POST`      |

## Payload

| Argument      | Example                                                                                                                         | Required | Description                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------ |
| `_id`        | `Qe3Wa3outaDMKzAZC`                                                                                                             | Optional | Email Id.                                                                |
| `name`        | `My-new-email`                                                                                                                  | Required | The name you wish to set for your email.                                 |
| `email`       | `mdyemaasil@rocket.chat`                                                                                                        | Required | The email to be used                                                     |
| `active`      | `true`                                                                                                                          | Required | Set whether or not the email is active.                                  |
| `description` | `A simple email to use`                                                                                                         | Optional | The description for this entry.                                          |
| `senderInfo`  | `email sender`                                                                                                                  | Optional | Sender info to be attached on outgoing emails.                           |
| `department`  | `marketing`                                                                                                                     | Optional | The department in which the email will be available to.                  |
| `smtp`        | `{ "password": "10fae4dc374fb87d", "port": 25, "secure": true, "server": "smtp.mailtrap.io", "username": "b5ef5safd6cb806c" }`  | Required | An object with your SMTP credentials to be used for outgoing emails.     |
| `imap`        | `{ "password": "10fae4374sdfb87d", "port": 993, "secure": true, "server": "imap.mailtrap.io", "username": "b5ef5aafd6cb806c" }` | Required |  An object having your IMAP credentials to be used for incomming emails. |

### Example Payload

```
{
    "name": "new email",
    "email": "mdyemaasil@rocket.chat",
    "active": false,
    "description": "This email has been set",
    "senderInfo": "email sender",
    "department": "awesome department",
    "smtp": {
        "password": "10fae4dc374fb87d",
        "port": 25,
        "secure": true,
        "server": "smtp.mailtrap.io",
        "username": "b5ef5safd6cb806c"
    },
    "imap": {
        "password": "10fae4374sdfb87d",
        "port": 993,
        "secure": true,
        "server": "imap.mailtrap.io",
        "username": "b5ef5aafd6cb806c"
    }
}
```

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/email-inbox' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "_id": "JdVkn_dkOlms_",
    "name": "my_new_email",
    "email": "myinboxemail@rocket.chat",
    "active": false,
    "smtp": {
        "password": "10fae4dc374fb87d",
        "port": 25,
        "secure": true,
        "server": "smtp.mailtrap.io",
        "username": "b5ef5safd6cb806c"
    },
    "imap": {
        "password": "10fae4374sdfb87d",
        "port": 993,
        "secure": true,
        "server": "imap.mailtrap.io",
        "username": "b5ef5aafd6cb806c"
    }
}'
```

## &#x20;Result

### Success

```javascript
{
    "_id": "JdVkn_dkOlms_",
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Permission**: Requires the user to have `manage-email-inbox` permission for the request to be made.
* **Duplicate**: You get a duplicate error when the email you are trying to set is already in record.

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
```
{
    "success": false,
    "error": "error-not-allowed"
}
```
{% endtab %}

{% tab title="Duplicate" %}
```
{
    "success": false,
    "error": "E11000 duplicate key error index: rocketchat.rocketchat_email_inbox.$email_1 dup key: { : \"mdyemail@rocket.chat\" }"
}
```
{% endtab %}

{% tab title="Invalid Inbox" %}
```
{
    "success": false,
    "error": "error-invalid-email-inbox"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version     | Description |
| ----------- | ----------- |
| 3.11.0-rc.0 | Added       |
