---
description: Search for a Visitor using their name, username, email or phone.
---

# Search for Visitors

It supports the [#pagination](../../#pagination "mention") parameters.

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/visitors.search` | `yes`         | `GET`       |

## Query Parameter

| Argument | Example               | Required | Description                                  |
| -------- | --------------------- | -------- | -------------------------------------------- |
| `term`   | `guest-1@company.com` | Optional | The visitor's name, username, email or phone |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitors.search?term=guest-1@company.com
```

## Example Result

```javascript
{
  "visitors": [
    {
      "_id": "KQv3cHgvW7CDQtGap",
      "username": "guest-1",
      "visitorEmails": [
        {
          "address": "guest-1@company.com"
        }
      ],
      "phone": [
        {
          "phoneNumber": "912235665456"
        }
      ],
      "name": "joey"
    }
  ],
  "count": 1,
  "offset": 0,
  "total": 1,
  "success": true
}
```
