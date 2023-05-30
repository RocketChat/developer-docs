# Start Import

Triggers the process of importing users, rooms and messages to the server.

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `/api/v1/startImport` | `yes`         | `POST`      |

## Payload

| `input`    | `{ "users": [], "channels": [] }`                                                                                                                                                                                                                                                                             | Required | Object containing two arrays: `users` and `channels`         |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------ |
| `users`    | <p><code>[ {</code></p><p><code>"user_id": "bradley.hilton", "username": "bradley.hilton", "email": "bradley.hilton@example.com", "is_deleted": false,</code></p><p><code>"is_bot": false,</code></p><p><code>"do_import": true,</code></p><p><code>"is_email_taken": false</code></p><p><code>} ]</code></p> | Required | Array of users, must be a property of the `input` object.    |
| `channels` | <p><code>[ {</code></p><p><code>"channel_id": "PyPSgdctSfa29vr59",</code></p><p><code>"name": "newRoom",</code></p><p><code>"is_archived": false,</code></p><p><code>"do_import": true,</code></p><p><code>"is_private": false,</code></p><p><code>"is_direct": false</code></p><p><code>} ]</code></p>       | Required | Array of channels, must be a property of the `input` object. |

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

| `channel_id`  | `"`4K2ovcvP5LqfxXnd5`"` | Required                      | The unique room identifier.                      |
| ------------- | ----------------------- | ----------------------------- | ------------------------------------------------ |
| `name`        | `"newRoom"`             | Required                      | The username for the user.                       |
| `creator`     | `"MF72rfNWNcv9EFZsx"`   | Optional default: `undefined` | The identifier of the channel owner.             |
| `is_private`  | `false`                 | Required                      | Is the described room private?                   |
| `is_direct`   | `false`                 | Required                      | Is the described room of type "Direct Messages"? |
| `is_archived` | `true`                  | Required                      | Is the described room archived?                  |
| `do_import`   | `false`                 | Required                      | Should the described room be imported?           |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.updateMember' \
      -d '{ "input": { "users": [ { "user_id": "bradley.hilton", "username": "bradley.hilton", "email": "bradley.hilton@example.com", "is_deleted": false, "is_bot": false, "do_import": true, "is_email_taken": false } ], "channels": [ { "channel_id": "WheeksNSvS5bsmYyw", "name": "newRoom", "is_archived": false, "do_import": true, "is_private": false, "is_direct":false } ] } } '
```

## Example Result

```javascript
{
  "success": true
}
```
