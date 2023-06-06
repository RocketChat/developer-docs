---
description: >-
  Get the extension information associated with the agent. Requires
  authentication.
---

# Get Omnichannel Agent Extension

| **URL**                           | **Requires Authentication** | **HTTP Method** |
| --------------------------------- | --------------------------- | --------------- |
| `/v1/omnichannel/agent/extension` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Data Type** | **Required** | **Description**           |
| ------------ | ------------- | ------------ | ------------------------- |
| `username`   | `string`      | Yes          | The username of the agent |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/omnichannel/agent/extension?count=10&offset=10' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "2hzS2maZM39wGggdd",
}'
```

### Example Response

```json
{
    "success": true,
}
```

### Error Response

401 Unauthorized
