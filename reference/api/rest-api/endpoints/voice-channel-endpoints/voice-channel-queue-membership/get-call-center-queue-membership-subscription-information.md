---
description: Use this endpoint to retrieve the Queue Membership Subscription Information
---

# Get Call Center Queue Membership Subscription Information

| **URL**                                        | **Requires Authentication** | **HTTP Method** |
| ---------------------------------------------- | --------------------------- | --------------- |
| `api/v1/voip/queues.getMembershipSubscription` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Data Type** | **Required** | **Description**                                    |
| ------------ | ------------- | ------------ | -------------------------------------------------- |
| `extension`  | `string`      | Required     | The phone extension for VoIP enabled node or user. |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/voip/queues.getMembershipSubscription' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "extension": "1293"
}'
```

### Example Response <a href="#example-result" id="example-result"></a>

```json
{
	"queues" : {
        "name": "event.queue",
        "loggedin": "event.loggedin",
        "available": "event.available",
        "callers": "event.available",
        "holdtime": "event.holdtime",
        "talktime": "event.talktime",
        "longestholdtime": "event.logestholdtime"
    },
	"extension": "1293"
}
```

### Error Response

401 Unauthorized
