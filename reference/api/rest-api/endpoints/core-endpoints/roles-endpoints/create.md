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

## Example Payload

```json
{
        "name": "Test Role",
        "scope": "Users",
        "description": "Testing Role for API",
        "mandatory2fa": false

    }
```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/roles.create' \
--header 'X-User-Id: rbAXPnMktTFbNpwtJ' \
--header 'X-Auth-Token: 3K3OqbQcU9H6FiZNEE5lxTTEfXyWxypWRJjvl_2ySOm' \
--header 'Content-Type: application/json' \
--data '{
        "name": "Test Role",
        "scope": "Users",
        "description": "Testing Role for API",
        "mandatory2fa": false

    }'
```

## Example Result

### Success

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

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Role Properties**: Occurs when the required [payload arguments](create.md#payload) are not provided when making the request.
* **Duplicate Role Names**: This occurs when the role's name already exists on the workspace.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Role Properties" %}
```json
{
    "success": false,
    "error": "The role properties are invalid. [error-invalid-role-properties]",
    "errorType": "error-invalid-role-properties"
}
```
{% endtab %}

{% tab title="Duplicate Role Names" %}
```json
{
    "success": false,
    "error": "Role name already exists [error-duplicate-role-names-not-allowed]",
    "errorType": "error-duplicate-role-names-not-allowed"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description                                                       |
| ------- | ----------------------------------------------------------------- |
| 0.70.0  | Added                                                             |
| 3.15.0  | Is no longer used to update roles                                 |
| 6.0.0   | Moved to [enteprise edition](https://www.rocket.chat/enterprise). |
