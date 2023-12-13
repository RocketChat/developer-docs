# Logout Other Clients

<table><thead><tr><th width="166">HTTP Method</th><th width="350">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.logoutOtherClients</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST http://localhost:3000/api/v1/users.logoutOtherClients\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

### Success

```javascript
{
    "token": "SnS70r0VkngGFrSbxVK-pdwFMEzhefcjQgdnXaPeAaq",
    "tokenExpires": "2021-12-27T14:33:09.851Z",
    "success": true
}
```

### Errors

The following error can occur.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
