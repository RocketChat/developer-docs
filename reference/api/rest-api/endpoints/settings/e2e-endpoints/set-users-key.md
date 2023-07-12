---
description: Sets the end-to-end encryption keys for the authenticated user.
---

# Set Users Key

| URL                                      | Requires Auth | HTTP Method |
| ---------------------------------------- | ------------- | ----------- |
| `api/v1/e2e.setUserPublicAndPrivateKeys` | `YES`         | `POST`      |

## Payload

| Argument      | Example         | Required   | Description      |
| ------------- | --------------- | ---------- | ---------------- |
| `public_key`  | `My-9UbLiK-k34` | `Optional` | The public key.  |
| `private_key` | `9R1V4t3_k3Y`   | `Optional` | The private key. |

### Example Payload

```
{
    "public_key": "My-9UbLiK-k34",
    "private_key": "9R1V4t3_k3Y"
}
```

## Example Call

```
curl --location --request POST 'http://localhost:3000/api/v1/e2e.setUserPublicAndPrivateKeys' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
--data-raw '{
    "public_key": "My-9UbLiK-k34",
    "private_key": "9R1V4t3_k3Y"
}'
```

## Example Result

### Success

```
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

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
