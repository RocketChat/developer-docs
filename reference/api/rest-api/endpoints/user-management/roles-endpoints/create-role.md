# Create Role

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Create a new role in the system.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/roles.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* This endpoint **doesn't** update existing roles. See [update-role.md](update-role.md "mention").
* You can't create new roles with the same name as existing roles. For example, it is not possible to create a new role with the name `admin` .
* The **scope** can either be `Users` or `Subscriptions`.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="207.33333333333331">Key</th><th width="212">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>newRole</code></td><td>The name of the new role.</td></tr><tr><td><code>scope</code></td><td><code>Subscriptions</code></td><td>The scope of the new role. The default value is <code>Users</code>.</td></tr><tr><td><code>description</code></td><td><code>Role description</code></td><td>A description for the new role.</td></tr><tr><td><code>mandatory2fa</code></td><td><code>true</code></td><td>Whether the role should have mandatory 2FA. The default value is <code>false</code>.</td></tr></tbody></table>

## Example Call

```powershell
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

## Example Response

### Success

```json
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

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Role Properties**: Occurs when the required [payload arguments](create-role.md#payload) are not provided when making the request.
* **Duplicate Role Names**: This occurs when the role's name already exists on the workspace.

{% tabs %}
{% tab title=" Authorization" %}
```json
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
