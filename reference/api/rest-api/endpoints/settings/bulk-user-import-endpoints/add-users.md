# Add Users

Adds user data to the import staging area. It requires the current import operation state to be either `new` or `ready`. If successful, it changes the operation state to `ready` .

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th>URL</th><th width="172">Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/import.addUsers</code></td><td><code>yes</code></td><td><code>POST</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

| Argument | Required | Description                                           |
| -------- | -------- | ----------------------------------------------------- |
| `users`  | `yes`    | An array of [user objects](add-users.md#user-object). |

#### **User Object**

| Attribute   | Type         | Required  | Example                                                  | Description                                              |
| ----------- | ------------ | --------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `username`  | String       |  Optional | "john.doe"                                               | The user's username.                                     |
| `emails`    | String Array | Required  | \["[john.doe@example.com](mailto:john.doe@example.com)"] | The user's email addresses.                              |
| `importIds` | String Array | Required  | \["1523"]                                                | A list of IDs that can identify the user.                |
| `name`      | String       | Optional  | "John Doe"                                               | The user's display name.                                 |
| `utcOffset` | Number       | Optional  | -3                                                       | The user's timezone, in number of hours relative to UTC. |
| `roles`     | String Array | Optional  | \["user"]                                                | A list of roles to assign to the user                    |
| `type`      | String       | Optional  | "user"                                                   | The user type, must be either "user" or "bot".           |
| `bio`       | String       | Optional  |                                                          | The user's profile bio.                                  |
| `password`  | String       | Optional  | "P@ssw0rd"                                               | A password to assign to this user.                       |
| `deleted`   | Boolean      | Optional  | false                                                    | Was the user deleted from the previous system?           |
| `avatarUrl` | String       | Optional  |                                                          | A URL pointing to the user's avatar picture.             |

## Example Payload

```bash
{
    "users": [
        {
            "username": "john.doe",
            "emails": [
                "john.doe@example.com"
            ],
            "importIds": [
                "1523"
            ],
            "name": "John Doe",
            "password": "P@ssw0rd"
        },
        {
            "username": "jane.doe",
            "emails": [
                "jane.doe@example.com"
            ],
            "importIds": [
                "1524"
            ],
            "name": "Jane Doe"
        }
    ]
}
```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/import.addUsers' \
--header 'x-auth-token: QizJozLOnWMi_2vWaLHhjfd-XYKT6XM40lTZ3zg1UMd' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \
--data-raw '{
    "users": [
        {
            "username": "john.doe",
            "emails": [
                "john.doe@example.com"
            ],
            "importIds": [
                "1523"
            ],
            "name": "John Doe",
            "password": "P@ssw0rd"
        },
        {
            "username": "jane.doe",
            "emails": [
                "jane.doe@example.com"
            ],
            "importIds": [
                "1524"
            ],
            "name": "Jane Doe"
        }
    ]
}'
```

**Here are some key points to note:**

1. A minimum of one **email address** and one **Import Id** is required. If any user is missing those, the endpoint will fail and no user will be added to the operation.
2. **Emails** and **usernames** will not be validated, but they must be unique or the user creation will fail.
3. If **roles** are added, they must be valid Rocket.Chat roles, or the endpoint will fail and no user will be added to the operation.
4. The default **roles** will be added to all users automatically.
5. If no **password** is added, a temporary random password will be generated automatically.
6. Users flagged as `deleted` will be created as **Deactivated** on Rocket.Chat.
7. Avatar URLs will not be fetched automatically. The workspace administrator uses the "**Download Pending Avatars**" button in **Administration > Workspace > Import** on the workspace after the import is completed.
8. **Import Ids** will not be used as Ids by Rocket.Chat, but you can query users by their import id with the [`users.info` endpoint](../../user-management/users-endpoints/get-users-info.md).

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

* **No Permission**: This occurs when the authenticated user doesn't have the  `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Initialize Import**: This occurs when there is no current import operation. See [New Import](new.md) to create a new import operation.

{% tabs %}
{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Initialize Import" %}
```
{
    "success": false,
    "error": "Import operation not initialized."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `6.3.0` | Added       |
