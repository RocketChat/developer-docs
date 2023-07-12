---
description: Get pages visited by livechat visitor
---

# Get pages visited by livechat visitor

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.pagesVisited/:roomId` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## URL Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `hhMKhHnnbY79mGs9K` | Required | Livechat room id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.pagesVisited/:roomId \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "pages": [],
    "count": 0,
    "offset": 0,
    "total": 0,
    "success": true
}
```

