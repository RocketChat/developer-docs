---
description: Updates the end-to-end encryption key for a user in a room.
---

# Update User E2E Key in Room

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `api/v1/e2e.updateGroupKey` | `YES`         | `POST`      |

## Payload

| Argument | Example             | Required   | Description             |
| -------- | ------------------- | ---------- | ----------------------- |
| `uid`    | `d26x6zSkaPSe5gCyy` | `Optional` | The user's Id.          |
| `rid`    | `9R1V4t3_k3Y`       | `Optional` | The Room Id.            |
| `key`    | `M4-Ubd4T3d-k39`    | \`Optional | The key to update with. |

### Example Payload

```
{
    "uid": "d26x6zSkaPSe5gCyy",
    "rid": "9R1V4t3_k3Y",
    "key": "M4-Ubd4T3d-k39"
}
```

## Example Call

```
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
