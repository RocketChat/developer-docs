---
description: Updates the end-to-end encryption key for a user in a room.
---

# Update User E2E Key in Room

| URL                         | Requires Auth                            | HTTP Method |
| --------------------------- | ---------------------------------------- | ----------- |
| `api/v1/e2e.updateGroupKey` | [`YES`](../../authentication-endpoints/) | `POST`      |

## Body Parameters

<table><thead><tr><th width="165">Argument</th><th>Example</th><th width="155">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>uid</code></td><td><code>d26x6zSkaPSe5gCyy</code></td><td>Required</td><td>The user's Id.</td></tr><tr><td><code>rid</code></td><td><code>9R1V4t3_k3Y</code></td><td>Required</td><td>The Room Id.</td></tr><tr><td><code>key</code></td><td><code>M4-Ubd4T3d-k39</code></td><td>Required</td><td>The key to update with.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/e2e.updateGroupKey' \
--header 'X-User-Id: Dtx5kwoQJGYQSw3Qh' \
--header 'X-Auth-Token: xR2x_iTXtoKLcNR21uhGKtUIt0X9r4x-r-UvhMwsVKV' \
--header 'Content-Type: application/json' \
--data-raw '{
    "uid": "d26x6zSkaPSe5gCyy",
    "rid": "9R1V4t3_k3Y",
    "key": "M4-Ubd4T3d-k39"
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
