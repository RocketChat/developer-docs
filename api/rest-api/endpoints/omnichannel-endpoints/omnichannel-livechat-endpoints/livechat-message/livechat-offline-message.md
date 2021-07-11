---
description: >-
  Sends the offline message when no agent is available to attend the omnichannel
  conversation
---

# Livechat Offline Message

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/offline.message` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `name` | `Livechat Visitor` | Required | Message `name`. |
| `email` | `visitor@rocket.chat` | Required | Message `email`. |
| `message` | `I need help` | Required | Message `text`. |

## Example payload

```javascript
{
  "name": "Livechat Visitor",
  "email": "visitor@rocket.chat",
  "message": "I need help"
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/offline.message \
     -d '{"name": "Livechat Visitor", "email": "visitor@rocket.chat", "message": "I need help"}'
```

## Example Result

```javascript
{
  "message": "Livechat offline message sent",
  "success": true
}
```



