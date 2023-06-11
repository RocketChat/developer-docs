---
description: Retrieves the pages your omnichannel user navigated on your website.
---

# Send Visitor navigation history

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/page.visited` | `no`          | `POST`      |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "rid": "vp3D9H8ud6HYvRpvq",
  "pageInfo": {
    "change": "url",
    "title": "",
    "location": {
      "href": "http://localhost:3000/packages/rocketchat_livechat/assets/demo.html#page-4"
    }
  }
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/page.visited \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "rid": "vp3D9H8ud6HYvRpvq", "pageInfo": { "change": "url", "title": "", "location": { "href": "http://localhost:3000/packages/rocketchat_livechat/assets/demo.html#page-4" } }}'
```

## Example Result

```javascript
{
    "success": true
}
```
