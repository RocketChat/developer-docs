---
description: Retrieve the visitor chat history.
---

# Get the visitor chat history

{% hint style="info" %}
It supports the [Offset, Count, and Sort Query Parameters](../../../team-collaboration/offset-and-count-and-sort-info.md).
{% endhint %}

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/visitors.chatHistory/room/room-id/visitor/visitor-id` | `yes` | `GET` |

## Query Parameter

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `iNKE8a6k6cjbqWhWd` | Required | The room's id. |
| `visitorId` | `iNKE8a6k6cjbqWhWd` | Required | The visitor's id. |

## Example Call

```bash
curl http://localhost:3000/api/v1/livechat/visitors.chatHistory/room/room-id/visitor/visitor-id
```

## Example Result

```javascript
{
  "history": [
    {
      "_id": "Yjc62ZSoWiHB8Q6xr",
      "msgs": 1,
      "usersCount": 2,
      "lm": "2019-12-09T20:30:32.058Z",
      "fname": "Visitor 1575554334960",
      "t": "l",
      "ts": "2019-12-09T20:30:32.058Z",
      "v": {
        "_id": "sAvPE8bjCJP5YwPnN",
        "username": "guest-2",
        "token": "iNKE8a6k6cjbqWhWd",
        "status": "online"
      },
      "cl": false,
      "open": true,
      "waitingResponse": true,
      "_updatedAt": "2019-12-09T20:30:32.808Z",
      "servedBy": {
        "_id": "w6YjbdZHjghjfNBAg",
        "username": "marcos.defendi",
        "ts": "2019-12-09T20:30:32.166Z"
      }
    }
  ],
  "count": 1,
  "offset": 0,
  "total": 14,
  "success": true
}
```

