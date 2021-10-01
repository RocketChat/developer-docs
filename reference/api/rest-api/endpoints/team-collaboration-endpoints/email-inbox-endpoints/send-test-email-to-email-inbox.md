# Send test email to email inbox

{% hint style="info" %}
Requires the user to have`manage-email-inbox`permission.
{% endhint %}

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/email-inbox.send-test/:_id` | `yes` | `POST` |

## Query Param <a id="query-param"></a>

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `email` | `info@rocket.chat` | Required | Email inbox address |

‌

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/email-inbox.search \
```

## 

‌

##  Result <a id="result"></a>

###  <a id="errors"></a>

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Permission**: Requires the user to have `manage-email-inbox` permission for the request to be made.
* Email inbox id required: Requires the user to have `manage-email-inbox` permission for the request to be made.

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

{% tab title="Email inbox id required" %}
```javascript
{
    "success": false,
    "error": "Resource not found"
}
```
{% endtab %}
{% endtabs %}

