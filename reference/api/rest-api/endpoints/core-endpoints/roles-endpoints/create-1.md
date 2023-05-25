# Role Update

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Update a role in the workspace.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/roles.update` | `yes`         | `POST`      |

## Payload

| Argument       | Example                    | Required                  | Description                                                       |
| -------------- | -------------------------- | ------------------------- | ----------------------------------------------------------------- |
| `roleId`       | `646c431fa8c3a3ba32d0e1c4` | Required                  |                                                                   |
| `name`         | `newRole`                  | Required                  | The updated name of the role.                                     |
| `scope`        | `Subscriptions`            | Optional Default: `Users` | The updated  scope of the role.                                   |
| `description`  | `Role description`         | Optional                  | A updated description for the role.                               |
| `mandatory2fa` | `true`                     | Optional Default: `false` | Whether the role should have a mandatory 2 Factor Authentication. |

## Example Payload

```json
{
        "roleId": "646c431fa8c3a3ba32d0e1c4",
        "name": "Test Role",
        "scope": "Users",
        "description": "Update Testing Role for API",
        "mandatory2fa": false

 }
```

## Example Call

```json
curl --location 'http://localhost:3000/api/v1/roles.update' \
--header 'X-User-Id: rbAXPnMktTFbNpwtJ' \
--header 'X-Auth-Token: 3K3OqbQcU9H6FiZNEE5lxTTEfXyWxypWRJjvl_2ySOm' \
--header 'Content-Type: application/json' \
--data '{
        "roleId": "646c431fa8c3a3ba32d0e1c4",
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

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Role Properties**: Occurs when the required [payload arguments](create-1.md#payload) are not provided when making the request.

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
{% endtabs %}

## Change Log

| Version | Description                                                        |
| ------- | ------------------------------------------------------------------ |
| 6.0.0   | Moved to [enterprise edition](https://www.rocket.chat/enterprise). |
