---
description: Get a Livechat Trigger by id.
---

# Get a Livechat Trigger

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/triggers/:_id` | `yes` | `GET` |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/triggers/Lk52shJFYyb55trw8
```

## Example Result

```javascript
{
    "trigger": {
        "_id": "Lk52shJFYyb55trw8",
        "name": "test",
        "description": "test",
        "enabled": true,
        "runOnce": true,
        "conditions": [
            {
                "name": "page-url",
                "value": ""
            }
        ],
        "actions": [
            {
                "name": "send-message",
                "params": {
                    "sender": "",
                    "msg": ""
                }
            }
        ],
        "_updatedAt": "2019-10-04T15:36:29.695Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 2.2.0 | Added |

