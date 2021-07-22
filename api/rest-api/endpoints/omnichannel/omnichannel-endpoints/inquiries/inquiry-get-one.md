---
description: Get one inquiry by room id.
---

# Inquiry Get One

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.getOne` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The room's id |

{% hint style="info" %}
If the user id is provided, the user must have the `view-l-room` permission.
{% endhint %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.getOne?roomId=ByehQjC44FwMeiLbX
```

## Example Result

```javascript
{
  "inquiry": {
    "_id": "EMXtMA7mPPNkQtWWq",
    "rid": "MA6HRhkEdRGATfEbh",
    "name": "inquiry test",
    "ts": "2019-12-13T18:54:25.352Z",
    "message": "",
    "status": "queued",
    "v": {
      "_id": "rLitbjv7e9WyLBCR4",
      "username": "guest-14",
      "token": "btzu0qdm0sjsn7aqm78kzr",
      "status": "offline"
    },
    "t": "l",
    "_updatedAt": "2019-12-13T19:33:13.255Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 2.4.0 | Added |

