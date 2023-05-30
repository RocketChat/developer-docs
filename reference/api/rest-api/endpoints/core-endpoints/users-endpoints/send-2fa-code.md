# Send 2fa code

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/users.2fa.sendEmailCode` | `yes`         | `POST`      |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/users.2fa.sendEmailCode\
      -d "emailOrUsername=email@rocket.chat"
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Errors <a href="#errors" id="errors"></a>

The following error can occur upon the endpoint.‌

* **Valid Email or Username**: Requires selector param for the request to be made.

{% tabs %}
{% tab title="Valid Email or Username " %}
```javascript
{
    "success": false,
    "error": "emailOrUsername is required [error-parameter-required]",
    "errorType": "error-parameter-required"
}
```
{% endtab %}
{% endtabs %}
