# Assign Role to User

Assign a role to a user. Optionally, you can set this role to a user for a specific room.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/roles.addUserToRole</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="198.33333333333331">Key</th><th width="218">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roleName</code><mark style="color:red;"><code>*</code></mark></td><td><code>guest</code></td><td><p>The role name. Alternatively, you can use the <code>roleId</code> parameter.</p><p><br><strong>Note</strong>: </p><ul><li>For default roles, the role name and ID are the same. For custom roles, the name and ID are different. </li><li>If you are setting a custom role for a user, make sure to enter the custom role ID and not the role name.</li></ul><p>Refer to <a href="https://docs.rocket.chat/setup-and-configure/roles-in-rocket.chat">Roles</a> for more information.</p></td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.chat</code></td><td>The user name.</td></tr><tr><td><code>roomId</code></td><td><code>dK7vNYXMdHGLdukpL</code></td><td>The room ID for which the user is assigned the role.</td></tr></tbody></table>

{% hint style="info" %}
By default, the three major room roles available in Rocket.Chat are **Owner**, **Leader**, and **Moderator**. Creating custom roles is an Enterprise workspace feature. Refer [Room Roles](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/room-roles) for more information.
{% endhint %}

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/roles.addUserToRole' \
--header 'x-auth-token: o9UKV2D7A5Ggl2vqgyEcItF-YPj4-R93NlMcA6XnE3B' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \
--data '{
    "roleName": "auditor-log", 
    "username": "test.funke", 
    "roomId": "64adb09baa5ad4273bfc0cbf" 
}'
```

## Example Response

```json
{
    "role": {
        "_id": "auditor-log",
        "scope": "Users",
        "description": "",
        "mandatory2fa": false,
        "name": "auditor-log",
        "protected": true,
        "_updatedAt": "2023-07-10T23:20:56.702Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.70.0  | Added       |
