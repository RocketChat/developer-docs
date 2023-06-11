---
description: >-
  Register a or get visitor info before creating a new Omnichannel room. You can
  set basic information such as name, phone, custom fields or the initial
  department
---

# Register a Livechat visitor

<table><thead><tr><th width="313.3333333333333">URL</th><th width="227">Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/livechat/visitor</code></td><td><code>no</code></td><td><code>POST</code></td></tr></tbody></table>

## Example payload

```javascript
{
  "visitor": {
    "name": "Livechat Visitor",
    "email": "visitor@rocket.chat",
    "department": "Department Name",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": "55 51 5555-5555",
    "customFields": [{
      "key": "address",
      "value": "Rocket.Chat street",
      "overwrite": true
    }]
  }
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/visitor \
    -d '{"visitor": {"name": "Livechat Visitor", "email": "visitor@rocket.chat", "token": "iNKE8a6k6cjbqWhWd", "department": "Department Name", "phone": "55 51 5555-5555", "customFields": [{ "key": "address", "value": "Rocket.Chat street", "overwrite": true }] }}'
```

## Example Result

```javascript
{
  "visitor": {
    "_id": "sGtcfEYz852uguxaS",
    "username": "guest-7",
    "_updatedAt": "2018-09-21T16:12:32.808Z",
    "token": "iNKE8a6k6cjbqWhWd",
    "department": "QtKnaPp36GazRnkLD",
    "phone": [
      {
        "phoneNumber": "55 51 5555-5555"
      }
    ],
    "visitorEmails": [
      {
        "address": "visitor@rocket.chat"
      }
    ],
    "name": "Livechat Visitor",
    "livechatData": {
      "address": "Rocket.Chat street"
    }
  },
  "success": true
}
```

After registering the visitor, [create the Omnichannel room](../livechat-room/livechat-room-info.md) using the same token used on this endpoint.
