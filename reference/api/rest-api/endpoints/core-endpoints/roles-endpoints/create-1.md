# Role Update

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Update a new role in the system.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/roles.update` | `yes`         | `POST`      |

## Payload

| Argument       | Example                    | Required                  | Description                                                       |
| -------------- | -------------------------- | ------------------------- | ----------------------------------------------------------------- |
| `roleId`       | `646c431fa8c3a3ba32d0e1c4` | Required                  |                                                                   |
| `name`         | `newRole`                  | Required                  | The name of the new role.                                         |
| `scope`        | `Subscriptions`            | Optional Default: `Users` | The scope of the new role.                                        |
| `description`  | `Role description`         | Optional                  | A description for the new role.                                   |
| `mandatory2fa` | `true`                     | Optional Default: `false` | Whether the role should have a mandatory 2 Factor Authentication. |

## Example Call

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.update\
     -d '{ "name": "update role" }' \
     -d '{ "scope": "Subscriptions" }' \
     -d '{ "description": "Update Role support tier 1" }' \
     -d '{ "roleId": "646c431fa8c3a3ba32d0e1c4" }' \
```

## Example Result

```javascript
{
    "role": {
        "_id": "646c431fa8c3a3ba32d0e1c4",
        "name": "update role",
        "scope": "Users",
        "description": "Update Role support tier 1",
        "protected": false,
        "mandatory2fa": false,
        "_updatedAt": "2023-05-23T05:33:33.730Z"
    },
    "success": true
}
```
