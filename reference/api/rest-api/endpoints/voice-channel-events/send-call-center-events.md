---
description: Use this endpoint to send the VoIP Client Events
---

# Send Call Center Events

| **URL**           | **Requires Authentication** | **HTTP Method** |
| ----------------- | --------------------------- | --------------- |
| `/v1/voip/events` | Yes                         | POST            |

### Request Headers

| Header       | Example        | Description                                                    |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Example** | **Required** | **Description**                                                                         |
| ------------ | ----------- | ------------ | --------------------------------------------------------------------------------------- |
| `rid`        | `string`    | Yes          | <p>The unique identifier for the room.</p><p>Example:<code>c9YW3rejo7HeL6ZDW</code></p> |
| `event`      | `string`    | Yes          | List of VoIP client events.                                                             |
| `comment`    | `string`    | No           | The comment                                                                             |

### VoIP Client Events

List of VoIP client Events available in enum format.

```json
{
	"VOIP-CALL-STARTED" = "voip-call-started",
	"VOIP-CALL-ENDED" = "voip-call-ended",
	"VOIP-CALL-DECLINED" = "voip-call-declined",
	"VOIP-CALL-ON-HOLD" = "voip-call-on-hold",
	"VOIP-CALL-UNHOLD" = "voip-call-unhold",
	"VOIP-CALL-DURATION" = "voip-call-duration",
}
```

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request POST 'localhost:3000/api/v1/voip/events' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "oWLW6v8c8oRGb4cC9",
    "event": "voip-call-started"
}'
```

### Error Response

401 Unauthorized
