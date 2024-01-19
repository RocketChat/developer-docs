---
description: Sets the end-to-end encryption keys for the authenticated user.
---

# Set Users Key

| URL                                      | Requires Auth                            | HTTP Method |
| ---------------------------------------- | ---------------------------------------- | ----------- |
| `api/v1/e2e.setUserPublicAndPrivateKeys` | [`YES`](../../authentication-endpoints/) | `POST`      |

## Body Parameters

<table><thead><tr><th>Argument</th><th>Example</th><th width="155">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>public_key</code></td><td><code>My-9UbLiK-k34</code></td><td>Required</td><td>The public key.</td></tr><tr><td><code>private_key</code></td><td><code>9R1V4t3_k3Y</code></td><td>Required</td><td>The private key.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/e2e.setUserPublicAndPrivateKeys' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
--data-raw '{
    "public_key": "My-9UbLiK-k34",
    "private_key": "9R1V4t3_k3Y"
}'
```

## Example Response

### Success

```json
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
