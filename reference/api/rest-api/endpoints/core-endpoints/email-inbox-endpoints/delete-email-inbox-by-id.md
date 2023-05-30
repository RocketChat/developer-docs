---
description: Deletes email inbox using id.
---

# Delete email inbox by id

{% hint style="info" %}
requires the user to have`manage-email-inbox`permission.
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/email-inbox/:_id` | `yes`         | `DELETE`    |

## Path Variable

| Argument | Example                    | Required | Description    |
| -------- | -------------------------- | -------- | -------------- |
| `_id`    | `60197e8ff82d6c83b96c53ff` | Required | Email inbox id |

## Example Call

```bash
curl -L -X DELETE 'http://localhost:3000/api/v1/email-inbox/61717dd1066bc500096cb36d' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
```

## Result

### Success

```javascript
{
    "_id": "61717dd1066bc500096cb36d",
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Permission**: Requires the user to have `manage-email-inbox` permission for the request to be made.
* **Email Not Found**: Triggered when the email entry with this `_id` is not found.

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
```
{
    "success": false,
    "error": "error-not-allowed"
}
```
{% endtab %}

{% tab title="Email Not Found" %}
```
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
