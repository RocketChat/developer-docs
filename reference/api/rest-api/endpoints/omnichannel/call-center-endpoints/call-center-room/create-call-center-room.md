---
description: >-
  Creates a VoIP room if rid is not passed, else gets an existing room based on
  rid and token.
---

# Create Call Center Room

| **URL**                                                                              | **Requires Authentication** | **HTTP Method** |
| ------------------------------------------------------------------------------------ | --------------------------- | --------------- |
| `/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba&agentId=6vHSSqdBHdm2R4gfi` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Query Parameters

| **Argument** | **Example** | **Required** | **Description**                                                                |
| ------------ | ----------- | ------------ | ------------------------------------------------------------------------------ |
| `token`      | `string`    | Yes          | The unique token generated for the Example: `867ad6a09fc4af29f6f1f2a9cf1deaba` |
| `agentId`    | `string`    | Yes          | The unique identifier for the agent Example:`6vHSSqdBHdm2R4gfi`                |

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request GET 'localhost:3000/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba&agentId=6vHSSqdBHdm2R4gfi' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json'
```

### Example Result

```json
{
    "success": true
}
```

### Error Response

401 Unauthorized
