---
description: Sends an array of messages
---

# Send an array of messages



| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/message` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | Visitor `token`. |
| `rid` | `zRAeTszXor8CCPceB` | Required | Room `_id`. |
| `msg` | `sending livechat message..` | Required | Message `text`. |
| `_id` |  | Optional | Message `_id`. |
| `agent` |  | Optional | Room `agent`. |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "rid": "zRAeTszXor8CCPceB",
  "msg": "sending livechat message.."
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/message \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "rid": "zRAeTszXor8CCPceB", "msg": "Hi!"}'
```

## Example Result

```javascript
{
    "message": {
        "_id": "XycfA5CetCPuEjqxw",
        "rid": "HPKh8QWZjZubfyxiC",
        "msg": "Hi!",
        "token": "qng7ig7dl5f8r7r1v8jnly",
        "alias": "Quin",
        "ts": "2021-07-26T17:23:59.368Z",
        "u": {
            "_id": "CaZYEFduit5Gkt7MC",
            "username": "guest-551",
            "name": "Quin"
        },
        "unread": true,
        "_updatedAt": "2021-07-26T17:23:59.467Z",
        "urls": [],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "Hi!"
                    }
                ]
            }
        ]
    },
    "success": true
}
```



