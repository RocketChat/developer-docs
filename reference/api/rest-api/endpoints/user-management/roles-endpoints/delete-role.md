# Delete Role

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/roles.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* Permission required: `access-permissions`
* Roles that have the `protected` value as `true` can't be deleted (such as: `admin`, `moderator`, `user` and so on).
* You cannot delete roles that are assigned to users. To do that, you must first remove this role from all the users.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="210.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roleId</code><mark style="color:red;"><code>*</code></mark></td><td><code>vEpePE7wK6vkYbDDx</code></td><td>The ID of an existing role.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://http://localhost:3000/api/v1/roles.delete' \
--header 'X-Auth-Token: x65a7F7aZZtW_H2hTgKEsp_RFxUkLPI6j0G5GNqvoyF' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--header 'Content-Type: text/plain' \
--data '{
    "roleId": "6579adcf2dd9f9d9514f6"
}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid RoleId**: This occurs when the `roleId` does not exist on your workspace.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Invalid RoleId" %}
```json
{
    "success": false,
    "error": "This role does not exist [error-invalid-roleId]",
    "errorType": "error-invalid-roleId"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.17.0  | Added       |
