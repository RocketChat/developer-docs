# Role Create

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Create a new role in the system.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/roles.create` | `yes`         | `POST`      |

**Note:**

* This endpoint **doesn't** update existing roles. See [create-1.md](create-1.md "mention").
* You can't create new roles with the same name as existing roles. _For example,_ it is not possible to create a new role with the name `admin` .
* The **scope** can either be `Users` or `Subscriptions`.

## Payload

| Argument       | Example            | Required                  | Description                                                       |
| -------------- | ------------------ | ------------------------- | ----------------------------------------------------------------- |
| `name`         | `newRole`          | Required                  | The name of the new role.                                         |
| `scope`        | `Subscriptions`    | Optional Default: `Users` | The scope of the new role.                                        |
| `description`  | `Role description` | Optional                  | A description for the new role.                                   |
| `mandatory2fa` | `true`             | Optional Default: `false` | Whether the role should have a mandatory 2 Factor Authentication. |

## Example Call

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.create \
     -d '{ "name": "newRole" }' \
     -d '{ "scope": "Subscriptions" }' \
     -d '{ "description": "Role description" }' \
```

## Example Result

```javascript
{
    "role": {
        "_id": "646c431fa8c3a3ba32d0e1c4",
        "name": "support1",
        "scope": "Subscriptions",
        "description": "Role support tier 1",
        "protected": false,
        "mandatory2fa": false,
        "_updatedAt": "2023-05-23T04:37:51.161Z"
    },
    "success": true
}
```

## Change Log

| Version | Description                       |
| ------- | --------------------------------- |
| 0.70.0  | Added                             |
| 3.15.0  | Is no longer used to update roles |
