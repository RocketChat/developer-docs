---
description: Retrieves the current Omnichannel agent information.
---

# Get Available Agent Information

| **URL**                            | **Requires Authentication** | **HTTP Method** |
| ---------------------------------- | --------------------------- | --------------- |
| `/v1/omnichannel/agents/available` | Yes                         | GET             |

### Query Parameters

| **Argument**       | **Data Type** | **Required** |
| ------------------ | ------------- | ------------ |
| `count`            | `number`      | No           |
| `offset`           | `number`      | No           |
| `sort`             | `string`      | No           |
| `query`            | `string`      | No           |
| `text`             | `string`      | No           |
| `includeExtension` | `string`      | No           |

### Example Call

```json
curl --location --request GET 'localhost:3000/api/v1/omnichannel/extensions?count=10&offset=10' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": "ByehQjC44FwMeiLbX"
}'
```

### Example Response

```json
{
    "agent": {
        "_id": "XycfA5CetCPuEjqxw",
        "username": "test.agent",
        "name": "agent123",
        "status": "online",
        "statusLivechat": "online",
        "emails": [
            {
                "address": "agent123@rocket.chat",
                "verified": true
            }
        ],       
        "livechat": {
            "maxNumberSimultaneousChat": "5"
        }
    },
    "success": true
}
```

### Error Response

401 Unauthorized
