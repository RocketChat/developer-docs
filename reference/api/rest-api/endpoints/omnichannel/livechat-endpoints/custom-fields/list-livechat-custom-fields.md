---
description: Get a list of Livechat custom fields.
---

# List livechat custom fields

It supports the [#pagination](../../../../#pagination "mention") parameters.



| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/custom-fields` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/custom-fields
```

## Example Result

```javascript
{
    "customFields": [
        {
            "_id": "address",
            "label": "address",
            "scope": "visitor",
            "visibility": "visible",
            "_updatedAt": "2019-10-03T14:12:47.595Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.2.0   | Added       |

##
