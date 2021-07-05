# Role Delete
Delete a role.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/roles.delete` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roleId` | `vEpePE7wK6vkYbDDx` | Required | The id of an existing role. |

**Note:**

* Roles that have the `protected` value as `true` **can't** be deleted (such as: `admin`, `moderator`, `user` and so on).
* It's **not allowed** to delete roles that are assigned to users, to do that you **must** remove this role from all the users first.

## Example Call

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.delete \
     -d '{ "roleId": "vEpePE7wK6vkYbDDx" }' \
```

## Example Result

```javascript
{
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 3.17.0 | Added |
