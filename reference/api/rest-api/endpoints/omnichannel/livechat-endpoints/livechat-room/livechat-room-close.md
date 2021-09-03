# Livechat Room Close

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/room.close` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `rid` | `XFzMqgn33DcsQkpJp` | Required | The room `_id`. |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |

## Example payload

```javascript
{
  "rid": "XFzMqgn33DcsQkpJp",
  "token": "iNKE8a6k6cjbqWhWd"
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/room.close \
     -d '{"rid": "XFzMqgn33DcsQkpJp", "token": "iNKE8a6k6cjbqWhWd"}'
```

## Example Result

```javascript
{
  "rid": "XFzMqgn33DcsQkpJp",
  "comment": "Closed by visitor",
  "success": true
}
```

