# Logout User

<table><thead><tr><th width="166">HTTP Method</th><th width="307">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/users.logout</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/users.logout\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

### Success

```json
{
    "message": "User JxemcN9PDCdfzJeZr has been logged out!",
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}
{% endtabs %}
