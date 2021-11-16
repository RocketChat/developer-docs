---
description: Retrieves E2E keys of logged in user
---

# Fetch your E2E Keys

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `api/v1/e2e.fetchMyKeys` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                            |
| -------------- | -------------- | -------- | ------------------------------------------------------ |
| `X-User-Id`    | `myuser-id`    | Required | User Id retuned from api login.                        |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/e2e.fetchMyKeys\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myumser-id'
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Error

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
