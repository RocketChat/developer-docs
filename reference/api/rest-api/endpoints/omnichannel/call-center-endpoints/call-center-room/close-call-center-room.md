---
description: Close a new Room
---

# Close Call Center Room

| **URL**               | **Requires Authentication** | **HTTP Method** |
| --------------------- | --------------------------- | --------------- |
| `/v1/voip/room.close` | Yes                         | POST            |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

```json
{
    "rid": "c9YW3rejo7HeL6ZDW",
    "token": "yHoawq4s9bDn4dM5H"
}
```

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request POST 'localhost:3000/api/v1/voip/room.close' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "c9YW3rejo7HeL6ZDW",
    "token": "yHoawq4s9bDn4dM5H"
}'
```

### Example Response

```json
{
    "rid": "c9YW3rejo7HeL6ZDW",
}
```

### Error Response

401 Unauthorized
