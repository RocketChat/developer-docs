---
description: Use this endpoint to check the VoIP management server connection status
---

# Check Management Server Connection

## Check Management Server Connection Status

| **URL**                                                                    | **Requires Authentication** | **HTTP Method** |
| -------------------------------------------------------------------------- | --------------------------- | --------------- |
| `api/v1/voip/managementServer/checkConnection?host&port&username&password` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Query Parameters



| **Argument** | **Data Type** | **Required** | **Description**                          |
| ------------ | ------------- | ------------ | ---------------------------------------- |
| `host`       | `string`      | Yes          | The hostname of the management server.   |
| `port`       | `string`      | Yes          | The port number of the management server |
| `username`   | `string`      | Yes          | The user name of the administrator user. |
| `password`   | `string`      | Yes          | The password of the administrator user.  |

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request GET 'localhost:3000/api/v1/voip/managementServer/checkConnection?host=localhost&port=3000&username=christysujitha&password=' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--data-raw ''
```

### Example Response <a href="#example-result" id="example-result"></a>

```json
{
	"status": "connected" | "connection-error",
	"error?": "string"
}
```

### Error Response

401 Unauthorized
