# Start Import

Triggers the process of importing users, rooms and messages to the server.

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `/api/v1/startImport` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

| `input` | <p></p><pre class="language-json"><code class="lang-json">{
"input": 
    { 
    "users": [{
    "user_id": "nStEdBR3SBSFvDej7n", "username": "testbh", "email": "testbh@gmail.com", 
    "is_deleted": false,
    "is_bot": false,
    "do_import": true,
    "is_email_taken": false
    }], 
    "channels": [{
    "channel_id": "WDuJLFkjwk6L7LdFC",
    "name": "dlp",
    "is_archived": false,
    "do_import": true,
    "is_private": false,
    "is_direct": false
    }] 
    }
}
</code></pre> | Required | The input object contains two arrays: `users` and `channels`. |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------- |

Each **user** described in the `users` array should contain the following properties:

| `user_id`        | `"bradley.hilton"`             | Required | The unique user identifier (which is the username, since the user may not have a proper `_id` yet). |
| ---------------- | ------------------------------ | -------- | --------------------------------------------------------------------------------------------------- |
| `username`       | `"bradley.hilton"`             | Required | The username for the user.                                                                          |
| `email`          | `"bradley.hilton@example.com"` | Required | The email address for the user.                                                                     |
| `is_deleted`     | `false`                        | Required | Was the described user deleted?                                                                     |
| `is_bot`         | `false`                        | Required | Is the described user a bot?                                                                        |
| `do_import`      | `true`                         | Required | Should the described user be imported?                                                              |
| `is_email_taken` | `false`                        | Required | Is there an existing user with the same email?                                                      |

Similarly, each **channel** described in the `channels` array should contain the following properties:

| `channel_id`  | `4K2ovcvP5LqfxXnd5` | Required                       | The unique room identifier.                                                                                                    |
| ------------- | ------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `name`        | `newRoom`           | Required                       | The name of the room.                                                                                                          |
| `creator`     | `MF72rfNWNcv9EFZsx` | Optional; Default: `undefined` | The identifier of the room owner.                                                                                              |
| `is_private`  | `false`             | Required                       | Is the described room private?                                                                                                 |
| `is_direct`   | `false`             | Required                       | Is the described room of type "[Direct Messages](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/direct-messages)"? |
| `is_archived` | `true`              | Required                       | Is the described room archived?                                                                                                |
| `do_import`   | `false`             | Required                       | Should the described room be imported?                                                                                         |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/startImport' \
--header 'x-auth-token: DTRPbgzQ0EDlTE3sdd3Nt7WfaWZE-lG1ayi9Pfa28Fm' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s' \
--header 'Content-Type: application/json' \
--data-raw '{
"input": 
    { 
    "users": [{
    "user_id": "testbh", "username": "testbh", "email": "testbh@gmail.com", 
    "is_deleted": false,
    "is_bot": false,
    "do_import": true,
    "is_email_taken": false
    }], 
    "channels": [{
    "channel_id": "WDuJLFkjwk6L7LdFC",
    "name": "dlp",
    "is_archived": false,
    "do_import": true,
    "is_private": false,
    "is_direct": false
    }] 
    }
}'
```

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

* **No Permission**: This occurs when the authenticated user doesn't have the  `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `3.0.0` | Added       |
