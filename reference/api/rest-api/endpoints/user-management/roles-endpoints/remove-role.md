# Remove Role

Remove a role from a user. Optionally, you can remove this role from a specified scope.

<table><thead><tr><th width="163">HTTP Method</th><th width="368">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/roles.removeUserFromRole</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `access-permissions`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="220.33333333333331">Key</th><th width="242">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roleName</code><mark style="color:red;"><code>*</code></mark></td><td><code>guest</code></td><td>The role name.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.chat</code></td><td>The user name.</td></tr><tr><td><code>roomId</code></td><td><code>dK7vNYXMdHGLdukpL</code></td><td>The scope where the role should be removed from.</td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type:application/json" \
     -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.removeUserFromRole \
     -d '{ "roleName": "guest" }' \
     -d '{ "username": "rocket.chat" }' \
```

## Example Response

```json
{
    "success": true
}
```
