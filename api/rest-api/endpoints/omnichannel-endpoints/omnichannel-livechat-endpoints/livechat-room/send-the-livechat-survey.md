# Send the Livechat survey

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/room.survey` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `rid` | `XFzMqgn33DcsQkpJp` | Required | The room `_id`. |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | The visitor `token`. |
| `data` | `[{"name": "satisfaction", "value":"3"}]` | Required | The survey `data`. |

## Example payload

```javascript
{
  "rid":"XFzMqgn33DcsQkpJp",
  "token": "iNKE8a6k6cjbqWhWd",
  "data": [
    {
      "name": "satisfaction",
      "value": "3"
    }
  ]
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/room.survey \
     -d '{"rid":"XFzMqgn33DcsQkpJp", "token": "iNKE8a6k6cjbqWhWd", "data": "[{"name": "satisfaction", "value": "3"}]"}'
```

## Example Result

```javascript
{
  "rid": "XFzMqgn33DcsQkpJp",
  "data": {
    "satisfaction": "3",
    "agentResposiveness": "5"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.70.0 | Added |

