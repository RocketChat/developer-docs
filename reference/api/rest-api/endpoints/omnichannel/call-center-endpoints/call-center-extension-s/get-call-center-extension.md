---
description: Fetch call center extension information
---

# Get Call Center Extension

| **URL**                     | **Requires Authentication** | **HTTP Method** |
| --------------------------- | --------------------------- | --------------- |
| `/v1/omnichannel/extension` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument**        | **Data Type**                          | **Required** |
| ------------------- | -------------------------------------- | ------------ |
| `userId\| username` | `string`                               | Yes          |
| `type`              | `'free' \| 'allocated' \| 'available'` | Yes          |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/omnichannel/extension? \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "userId": "2hzS2maZM39wGggdd",
    "type": "free"
}'
```

### Example Response

```json
{
    "extensions": "10023"
```

### Error Response

401 Unauthorized
