---
description: Takes an open inquiry.
---

# Take Inquiry

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.take` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `inquiryId` | `ByehQjC44FwMeiLbX` | Required | The inquiry's id |
| `userId` | `ByehQjCfsd876sfd` | Optional | The user's \(agent\) id to take the inquiry. |

{% hint style="info" %}
 If the user id is provided, the user must have the `view-l-room` permission.
{% endhint %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.take \
     -d '{ "inquiryId": "ByehQjC44FwMeiLbX" }'
```

## Example Result

```javascript
{
    "inquiry": {
        "_id": "wbKmn6pAZ8jyJuANG",
        "rid": "S4wwL9WNY98uoHgJg",
        "message": "test",
        "name": "teste",
        "ts": "2019-06-10T23:09:06.482Z",
        "agents": [
            "hjwGZafNqExtFNmN7",
            "26KdXgrQXhddy2MfQ"
        ],
        "status": "open",
        "v": {
            "_id": "2iZSexGXjW7EJnRwM",
            "username": "guest-3",
            "token": "RtQzkfQYKG4WpNMEW",
            "status": "online"
        },
        "t": "l",
        "_updatedAt": "2019-06-10T23:09:07.480Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.2.0 | Added |

