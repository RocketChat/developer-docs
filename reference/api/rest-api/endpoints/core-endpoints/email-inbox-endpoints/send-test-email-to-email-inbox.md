---
description: Sends test email to email inbox
---

# Send test email to email inbox

{% hint style="info" %}
Requires the user to have`manage-`email`-inbox`permission.


{% endhint %}

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `api/v1/email-inbox.send-test/:_id` | `yes`         | `GET`       |

## Path Variable

| Argument | Example                    | Required | Description    |
| -------- | -------------------------- | -------- | -------------- |
| `_id`    | `60197e8ff82d6c83b96c53ff` | Required | Email inbox id |

## Example Call

```bash
curl -L -X POST 'https://multiverse.rocket.chat/api/v1/email-inbox.send-test/60197e8ff82d6c83b96c53ff' \
-H 'X-User-Id: Dtx5kwoQJGYQSw3Qh' \
-H 'X-Auth-Token: do7rPm9t63Iqil5K5wbj3YBXUstAqo-GSKTcGSdDTtl' \
```

## Result

### Success

```javascript
{
    "_id": "60197e8ff82d6c83b96c53ff",
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
{% endtabs %}

## Change Log

| Version     | Description |
| ----------- | ----------- |
| 3.11.0-rc.0 | Added       |
