---
description: Logs out other clients.
---

# Logout Other Clients

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/users.logoutOtherClients` | `YES` | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST http://localhost:3000/api/v1/users.logoutOtherClients\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "token": "SnS70r0VkngGFrSbxVK-pdwFMEzhefcjQgdnXaPeAaq",
    "tokenExpires": "2021-12-27T14:33:09.851Z",
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
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

