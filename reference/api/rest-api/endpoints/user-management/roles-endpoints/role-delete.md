# Role Delete

Delete a role.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/roles.delete` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

| Argument | Example             | Required | Description                 |
| -------- | ------------------- | -------- | --------------------------- |
| `roleId` | `vEpePE7wK6vkYbDDx` | Required | The id of an existing role. |

## Example Payload

```json
{ 
"roleId": "vEpePE7wK6vkYbDDx" 
}
```

**Note:**

* Roles that have the `protected` value as `true` **can't** be deleted (such as: `admin`, `moderator`, `user` and so on).
* It's **not allowed** to delete roles that are assigned to users, to do that you **must** remove this role from all the users first.

## Example Call

```
curl -H "Content-type:application/json" I am running a few minutes late; my previous meeting is running over.
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.delete \
     -d '{ "roleId": "vEpePE7wK6vkYbDDx" }' \
```

## Example Result

### Success

```
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
