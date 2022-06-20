---
description: Deletes a custom user status
---

# Delete custom user status

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/custom-user-status.delete` | `YES` | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/custom-user-status.delete\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
 -d "customUserStatusId=EscbQinc8jmeXbpt7"
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Errors

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **customUserStatusId param**: Requires a custom user status `customUserStatusId`.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="customUserStatusId pram" %}
```javascript
{
    "success": false,
    "error": "The \"customUserStatusId\" params is required!"
}
```
{% endtab %}
{% endtabs %}

