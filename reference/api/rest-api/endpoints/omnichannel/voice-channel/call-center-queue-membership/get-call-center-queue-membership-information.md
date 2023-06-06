---
description: Retrieves the Queue Membership Information
---

# Get Call Center Queue Membership Information

| **URL**                                             | **Requires Authentication** | **HTTP Method** |
| --------------------------------------------------- | --------------------------- | --------------- |
| `api/v1/voip/queues.getQueuedCallsForThisExtension` | Yes                         | GET             |

### Request Headers

| **Header**   | **Example**    | **Description**                                                |
| ------------ | -------------- | -------------------------------------------------------------- |
| X-Auth-Token | `myauth-token` | Your token (returned after you log in through the API)         |
| X-User-Id    | `myuser-name`  | Your username hash (returned after you log in through the API) |

### Payload

| **Argument** | **Data Type** | **Required** | **Description**              |
| ------------ | ------------- | ------------ | ---------------------------- |
| `extension`  | `string`      | Required     | The phone extension for VoIP |

### Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request GET 'localhost:3000/api/v1/voip/queues.getQueuedCallsForThisExtension' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "extension": "12234"
}'
```

### Example Response <a href="#example-result" id="example-result"></a>

```json
{
  "extension": "12234",
  "queueCount": "1",
  "callWaitingCount": "2"
 }
```

### Error Response

401 Unauthorized
