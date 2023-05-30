---
description: Sets omnichannel visitor's satus
---

# Set visitor status

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/visitor.status` | `no`          | `POST`      |

## Example payload

```javascript
{
"token": "8s7e9ony6ctl27e1qf8kue",
"status": "busy"
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/visitor.status
    -d '{"token": "8s7e9ony6ctl27e1qf8kue", "status": "busy"}'
```

## Example Result

```javascript
{
    "token": "8s7e9ony6ctl27e1qf8kue",
    "status": "busy",
    "success": true
}
```
