---
description: Get info about a custom field.
---

# Get info about a custom field

| URL                                   | Requires Auth | HTTP Method |
| ------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/custom-fields/:_id` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/custom-fields/address
```

## Example Result

```javascript
{
    "customField": {
        "_id": "address",
        "label": "address",
        "scope": "visitor",
        "visibility": "visible",
        "_updatedAt": "2019-10-03T14:12:47.595Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
