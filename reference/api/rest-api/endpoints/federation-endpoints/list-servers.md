---
description: List all the server the user already saved
---

# List servers

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `/api/v1/federation/listServersByUser` | y`es`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/federation/listServersByUser
```

## Example Result

```javascript
{
    "servers": [
        {
            "name": "my-local.server",
            "default": true,
            "local": true
        },
        {
            "name": "matrix.org",
            "default": true,
            "local": false
        },
        {
            "name": "gitter.im",
            "default": true,
            "local": false
        },
        {
            "name": "libera.chat",
            "default": true,
            "local": false
        },
        {
            "name": "my-added-server.rocket.chat",
            "default": false,
            "local": false
        }
    ],
    "success": true
}

```

<table><thead><tr><th></th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
