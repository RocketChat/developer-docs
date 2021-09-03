---
description: Sends an array of messages
---

# Send an array of messages

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/messages` | yes | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example payload

```javascript
{
    "visitor": {"token": "8s7e9ony6ctl27e1qf8kue"},
    "messages": [{"msg": "test" }]
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/messages \
     -d '{
    "visitor": {"token": "8s7e9ony6ctl27e1qf8kue"},
    "messages": [{"msg": "test" }]
}'
```

## Example Result

```javascript
{
    "messages": [
        {
            "username": "guest-537",
            "msg": "test",
            "ts": "2021-08-02T20:24:44.125Z"
        }
    ],
    "success": true
}
```



