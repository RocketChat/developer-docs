---
description: Dismisses a banner
---

# Dismiss a banner

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `api/v1/banners.dismiss` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/banners.dismiss\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d "bannerId=ByehQjC44FwMeiLbX"
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing Key**: Requires `bannerId` for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```


{% endtab %}

{% tab title="Missing key 'bannerId'" %}
```javascript
{
    "success": false,
    "error": "Match error: Missing key 'bannerId'"
}
```


{% endtab %}
{% endtabs %}
