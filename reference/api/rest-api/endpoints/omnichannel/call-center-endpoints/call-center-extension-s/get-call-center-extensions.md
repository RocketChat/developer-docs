---
description: Get the list of call center enabled extensions
---

# Get call center Extensions

| **URL**                      | **Description**            | **HTTP Method** |
| ---------------------------- | -------------------------- | --------------- |
| `/v1/omnichannel/extensions` | Fetch VoIP Extensions data | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Query Parameters

| **Argument** | **Data Type** | **Required** |
| ------------ | ------------- | ------------ |
| `count`      | `number`      | No           |
| `offset`     | `number`      | No           |
| `sort`       | `string`      | No           |
| `query`      | `string`      | No           |
| `status`     | `string`      | No           |
| `agentId`    | `string`      | No           |
| `queues`     | `string`      | No           |
| `extension`  | `string`      | No           |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/omnichannel/extensions?count=10&offset=10' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json'
```

### Example Response

```json
{
    "success": true
}
```

### Error Response

401 Unauthorized
