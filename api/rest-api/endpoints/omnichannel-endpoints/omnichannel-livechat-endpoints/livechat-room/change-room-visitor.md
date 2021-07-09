# Change Room Visitor

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/room.visitor` | `yes` | `PUT` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `rid` | `XFzMqgn33DcsQkpJp` | Required | The room `_id`. |
| `visitorId` | `iNKE8a6k6cjbqWhWd` | Required | The visitor `_id_`. |

## Example payload

```javascript
{
  "rid":"2xC3rGZRiJztFYP5t",
  "visitorId": "qpdxquZygF4j9aFTR",
}
```

## Example Call

```bash
curl "http://localhost:3000/api/v1/livechat/room.visitor" \
  -X PUT \
  -d "{\"rid\":\"2xC3rGZRiJztFYP5t\",\"visitorId\":\"qpdxquZygF4j9aFTR\"}" \
  -H "X-User-Id: YE3xHYifqk4ic3e3B" \
  -H "X-Auth-Token: DVeIk8owiiudy0_lP981GkTWXLTARcCNkef5XuIDVY5" \
  -H "Content-Type: application/json"
```

## Example Result

```javascript
{
  "rid": "XFzMqgn33DcsQkpJp",
  "room": {
    "rid": "XFzMqgn33DcsQkpJp",
    "v": {
      "_id": "qpdxquZygF4j9aFTR",
      "username": "guest-2",
      "token": "gn33Dcsgn33DcsQk"
    }
  },
  "success": true
}
```



