---
description: Retrieves the User Registration Information for the User ID.
---

# Call Center Registration Information



| **URL**                                                   | **Requires Authentication** | **HTTP Method** |
| --------------------------------------------------------- | --------------------------- | --------------- |
| `/api/v1/connector.extension.getRegistrationInfoByUserId` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Data Type** | **Required** | **Description**                                                   |
| ------------ | ------------- | ------------ | ----------------------------------------------------------------- |
| `id`         | `String`      | Yes          | The identifier of the user whose registration is being retrieved. |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/connector.extension.getRegistrationInfoByUserId' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": "ByehQjC44FwMeiLbX"
}'
```

### Example Response

The response for this API contains the VoIP User Registration information.

```json
{
	"host": "omni-asterisk.dev.rocket.chat",
	"callServerConfig":{
		"websocketPort": "443",
		"websocketPath": "wss://omni-asterisk.dev.rocket.chat/ws"
	},
	"extensionDetails":{
		"extension": "12342",
		"password": "my$up3erP@ssw0rd",
		"authtype": "password",
		"state": "Not in use"
	}
}
```

### Error Response

401 Unauthorized

