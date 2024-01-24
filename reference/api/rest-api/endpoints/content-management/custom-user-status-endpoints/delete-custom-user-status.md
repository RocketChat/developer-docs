---
description: Deletes a custom user status
---

# Delete custom user status

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `api/v1/custom-user-status.delete` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

### ayload <a href="#payload" id="payload"></a>

| Argument           | Example                  | Required | Description                    |
| ------------------ | ------------------------ | -------- | ------------------------------ |
| customUserStatusId | 65b10ba40d645cae0192dcd1 | Required | The `_id` of the custom status |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/custom-user-status.delete' \
--header 'x-auth-token: Tkezpbi_kO09J4PcQM72UESdz9Dit6tT1uEzYMLnqzI' \
--header 'x-user-id: KDg2PcfJn8egn69Mo' \
--header 'Content-Type: application/json' \
--data '{
    "customUserStatusId": "65b10ba40d645cae0192dcd1"
}'
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
