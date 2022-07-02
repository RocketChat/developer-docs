---
description: Create agent-extension association information. Requires authentication
---

# Update Omnichannel Agent Extension

| **URL**                           | **Requires Authentication** | **HTTP Method** |
| --------------------------------- | --------------------------- | --------------- |
| `/v1/omnichannel/agent/extension` | Yes                         | POST            |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument**        | **Data Type** | **Required** | **Description**               |
| ------------------- | ------------- | ------------ | ----------------------------- |
| `userId\| username` | `string`      | Yes          | The user name or user Id      |
| `extension`         | `string`      | Yes          | The phone extension for VoIP  |

### Example Call

```json
curl --location --request POST 'localhost:3000/api/v1/omnichannel/agent/extension' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "oWLW6v8c8oRGb4cC9",
}'
```

### No Response
