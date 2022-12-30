# Delete a visitor

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/visitor/:token` | `no`          | `Delete`    |

## Query Parameters

| Argument | Example                  | Required | Description          |
| -------- | ------------------------ | -------- | -------------------- |
| `token`  | `8s7e9ony6ctl27e1qf8kue` | Required | The visitor `token`. |

## Example Call

```bash
curl -X DELETE http://localhost:3000/api/v1/livechat/visitor/:token
```

## Example Result

```javascript
{
    "visitor": {
        "_id": "47Dajwh9DjpnTAugW",
        "ts": "2021-07-18T13:28:38.962Z"
    },
    "success": true
}
```
