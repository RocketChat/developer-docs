---
description: Chatbot agent forwards the chat to a human agent
---

# Livechat Room Forward

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/room.forward` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `XFzMqgn33DcsQkpJp` | Required | The room `_id`. |
| `userId` | `iNKE8a6k6cjbqWhWd` | Optional | The new `agent ID`. |
| `departmentId` | `wXpPLofkffqWAwDNF` | Optional | The new `department ID`. |

## Example payload

```javascript
{
  "roomId": "XFzMqgn33DcsQkpJp",
  "userId": "iNKE8a6k6cjbqWhWd"
}
```

```javascript
{
  "roomId": "XFzMqgn33DcsQkpJp",
  "departmentId": "wXpPLofkffqWAwDNF"
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/room.forward \
     -d '{"roomId": "XFzMqgn33DcsQkpJp", "userId": "iNKE8a6k6cjbqWhWd"}'
```

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/room.forward \
     -d '{"roomId": "XFzMqgn33DcsQkpJp", "departmentId": "wXpPLofkffqWAwDNF"}'
```

## Example Result

```javascript
{
  "success": true
}
```

