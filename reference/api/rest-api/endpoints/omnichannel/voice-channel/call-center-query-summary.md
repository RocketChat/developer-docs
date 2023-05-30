---
description: Use this endpoint to get the VoIP query summary
---

# Call Center Query Summary

| **URL**                         | **Requires Authentication** | **HTTP Method** |
| ------------------------------- | --------------------------- | --------------- |
| `api/v1/voip/queues.getSummary` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Example Call

```
curl --location --request GET 'localhost:3000/api/v1/voip/queues.getSummary' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' 
```

### Example Result

```json
{
	"name": "string",
	"loggedin": "string",
	"available": "string",
	"callers": "string",
	"holdtime": "string",
	"talktime": "string",
	"logestholdtime": "string"
}
```
