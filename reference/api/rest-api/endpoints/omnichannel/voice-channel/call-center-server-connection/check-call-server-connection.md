---
description: Use this endpoint to check the SIP call server connection status.
---

# Check Call Server Connection

## Check Call Server Connection Status

| **URL**                                                                    | **Requires Authentication** | **HTTP Method** |
| -------------------------------------------------------------------------- | --------------------------- | --------------- |
| `api/v1/voip/managementServer/checkConnection?host&port&username&password` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Query Parameters

| **Argument**   | **Example** | **Required** | **Description**                   |
| -------------- | ----------- | ------------ | --------------------------------- |
| `websocketUrl` | `string`    | Yes          | The Websocket URL                 |
| `host`         | `string`    | Yes          | The hostname of the Call Server.  |
| `port`         | `string`    | Yes          | The port number of the Websocket. |
| `path`         | `string`    | Yes          | The path of the Websocket.        |

### Example Call <a href="#example-result" id="example-result"></a>

```json
curl --location --request GET 'localhost:3000/api/v1/voip/callServer/checkConnection?websocketUrl=wss://omni-asterisk.dev.rocket.chat/ws' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "c9YW3rejo7HeL6ZDW",
    "token": "yHoawq4s9bDn4dM5H"
}'
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
