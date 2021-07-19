---
description: Retrieves the current Livechat agent data.
---

# Agent Info



| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/agent.info/:rid/:token` | `no` | `GET` |

## Path Variables 

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `rid` | `zRAeTszXor8CCPceB` | Required | The room `_id`. |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/agent.info/:rid/:token
```

## Example Result

```javascript
{
    "agent": {
        "_id": "XycfA5CetCPuEjqxw",
        "emails": [
            {
                "address": "faria@rocket.chat",
                "verified": true
            }
        ],
        "status": "online",
        "name": "Faria",
        "username": "faria.masood",
        "livechat": {
            "maxNumberSimultaneousChat": "5"
        }
    },
    "success": true
}
```

