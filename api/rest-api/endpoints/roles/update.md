# Role Update
Update an existing role in the system.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/roles.update` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roleId` | `vEpePE7wK6vkYbDDx` | Required | The id of an existing role. |
| `name` | `newRole` | Optional | A new name for for an existing role. |
| `scope` | `Subscriptions` Default: `Users`| Optional | A new scope for an existing role. |
| `description` | `New role description` | Optional | A new description for an existing role. |
| `mandatory2fa` | `true` Default: `false`| Optional | Whether the role should have a mandatory 2 Factor Authentication. |

**Note:**

* Roles that have the `protected` value as `true` **can't** be updated (such as: `admin`, `moderator`, `user` and so on).
* It's **not allowed** to update the name of a role to an existing name of another role. For example: updating `newRole` to `user` **is not** possible.

## Example Call

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.update \
     -d '{ "roleId": "vEpePE7wK6vkYbDDx" }' \
     -d '{ "name": "newRole" }' \
     -d '{ "scope": "Subscriptions" }' \
     -d '{ "description": "Role description" }' \
     -d '{ "mandatory2fa": true }' \
```

## Example Result

```javascript
{
    "role": {
        "_id": "vEpePE7wK6vkYbDDx", 
        "name": "newRole",
        "scope": "Subscriptions",
        "description": "New role description",
        "protected": false,
        "mandatory2fa": true,
        "_updatedAt": "2021-06-09T12:20:38.128Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 3.16.0 | Added |
