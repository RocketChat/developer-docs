---
description: Retrieve the visitor navigation history
---

# Livechat visitor navigation history

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/visitors.pagesVisited` | `yes` | `GET` |

## Query Parameter

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `iNKE8a6k6cjbqWhWd` | Required | The room's id. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitors.pagesVisited?roomId=iNKE8a6k6cjbqWhWd
```

## Example Result

```javascript
{
    "pages": [
        {
            "_id": "7sixPtdqiCcfSRrWJ",
            "t": "livechat_navigation_history",
            "rid": "wBCg9ZgXT7Mvqz5Xu",
            "ts": "2019-10-21T19:51:22.298Z",
            "msg": "App test - http://localhost:8601/",
            "u": {
                "_id": "rocket.cat",
                "username": "rocket.cat"
            },
            "groupable": false,
            "navigation": {
                "page": {
                    "change": "url",
                    "title": "Test",
                    "location": {
                        "href": "http://localhost:8601/"
                    }
                },
                "token": "9vcfr6wb3sllv5t14d9x3"
            },
            "_hidden": true,
            "_updatedAt": "2019-10-21T19:51:22.298Z"
        }
    ],
    "success": true
}
```

