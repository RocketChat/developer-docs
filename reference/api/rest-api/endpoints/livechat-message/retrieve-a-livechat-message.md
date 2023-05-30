---
description: Retrieve a specific message
---

# Retrieve a Livechat message

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/message/:_id` | `no`          | `GET`       |

## URL Parameters

| Argument | Example             | Required | Description    |
| -------- | ------------------- | -------- | -------------- |
| `_id`    | `AgRFdj96mbHDPrTHq` | Required | Message `_id`. |

## Query Parameters

| Argument | Example                  | Required | Description      |
| -------- | ------------------------ | -------- | ---------------- |
| `token`  | `8s7e9ony6ctl27e1qf8kue` | Required | Visitor `token`. |
| `rid`    | `mmqCzYgiL8fzRYfuY`      | Required | Room `_id`.      |

## Example Call

```bash
curl -X GET \
     http://localhost:3000/api/v1/livechat/message/:_id?token=8s7e9ony6ctl27e1qf8kue&rid=mmqCzYgiL8fzRYfuY
     
```

## Example Result

```javascript
{
    "message": {
        "_id": "AgRFdj96mbHDPrTHq",
        "rid": "mmqCzYgiL8fzRYfuY",
        "msg": "hi",
        "token": "8s7e9ony6ctl27e1qf8kue",
        "alias": "Mary",
        "ts": "2021-07-13T16:20:26.672Z",
        "u": {
            "_id": "47Dajwh9DjpnTAugW",
            "username": "guest-165",
            "name": "Mary"
        },
        "unread": true,
        "_updatedAt": "2021-07-13T16:20:26.776Z",
        "urls": [],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "hi"
                    }
                ]
            }
        ]
    },
    "success": true
}
```
