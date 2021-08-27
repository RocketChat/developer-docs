---
description: >-
  Remove a role from a user. Optionally, you can unset this role for a specified
  scope.
---

# Role Remove

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/roles.removeUserFromRole` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roleName` | `guest` | Required | The role name |
| `username` | `rocket.chat` | Required | The user name |
| `roomId` | `dK7vNYXMdHGLdukpL` | Optional | The scope where the role should be unset |

## Example call to get all the roles after a given date

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.removeUserFromRole \
     -d '{ "roleName": "guest" }' \
     -d '{ "username": "rocket.chat" }' \
```

## Example Result

```javascript
{
    "success": true
}
```

