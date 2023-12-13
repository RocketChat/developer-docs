# Update Role

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/roles.update</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `access-permissions`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="201.33333333333331">Key</th><th width="230">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roleId</code><mark style="color:red;"><code>*</code></mark></td><td><code>646c431fa8c3a3ba32d0e1c4</code></td><td>The role ID that you want to update.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>newRole</code></td><td>The updated name of the role.</td></tr><tr><td><code>scope</code></td><td><code>Subscriptions</code></td><td>The updated  scope of the role. The default value is <code>Users</code>.</td></tr><tr><td><code>description</code></td><td><code>Role description</code></td><td>A updated description for the role.</td></tr><tr><td><code>mandatory2fa</code></td><td><code>true</code></td><td>Whether the role should have a mandatory 2FA. The default role is <code>false</code>.</td></tr></tbody></table>

## Example Call

```powershell
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

## Example Response

### Success

```json
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

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Role Properties**: Occurs when the required [payload arguments](update-role.md#payload) are not provided when making the request.

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
{% endtabs %}

## Change Log

<table><thead><tr><th width="343">Version</th><th>Description</th></tr></thead><tbody><tr><td>6.0.0</td><td>Moved to <a href="https://www.rocket.chat/enterprise">enterprise edition</a>.</td></tr></tbody></table>
