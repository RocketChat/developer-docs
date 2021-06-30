---
description: Gives a list of tags
---

# List of Tags



| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/tags.list` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "tags": [
        {
            "_id": "pXkCRLGxD34y2FEZq",
            "name": "Valuable  lead",
            "description": "high chances of conversion",
            "numDepartments": 1,
            "departments": [
                "GgYvrkAF63aeQmsh4"
            ],
            "_updatedAt": "2021-06-28T16:43:57.688Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

