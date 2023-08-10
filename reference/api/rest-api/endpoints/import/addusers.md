# Add Users

Adds user data to the import staging area;
Requires the current import operation state to be either `new` or `ready`;
Changes the operation state to `ready` if successful;

Requires the `run-import` permission.


| URL                       | Requires Auth | HTTP Method |
| ------------------------- | ------------- | ----------- |
| `/api/v1/import.addUsers` | `yes`         | `POST`      |

## Payload

| Argument | Required | Description                                                   |
| -------- | -------- | ------------------------------------------------------------- | 
| `users`  | `yes`    | A list of user objects matching the structure detailed below. |

### User Object

| Attribute   | Type         | Required | Example                  | Description                                              |
| ----------- | ------------ | -------- | ------------------------ | -------------------------------------------------------- |
| `username`  | String       | `no`     | "john.doe"               | The user's username.                                     |
| `emails`    | String Array | `yes`    | ["john.doe@example.com"] | The user's email addresses.                              |
| `importIds` | String Array | `yes`    | ["1523"]                 | A list of IDs that can identify the user.                |
| `name`      | String       | `no`     | "John Doe"               | The user's display name.                                 |
| `utcOffset` | Number       | `no`     | -3                       | The user's timezone, in number of hours relative to UTC. |
| `roles`     | String Array | `no`     | ["user"]                 | A list of roles to assign to the user                    |
| `type`      | String       | `no`     | "user"                   | The user type, must be either "user" or "bot".           |
| `bio`       | String       | `no`     |                          | The user's profile bio.                                  |
| `password`  | String       | `no`     | "P@ssw0rd"               | A password to assign to this user.                       |
| `deleted`   | Boolean      | `no`     | false                    | Was the user deleted from the previous system?           |
| `avatarUrl` | String       | `no`     |                          | An URL pointing to the user's avatar picture.            |


**Notes**
1. Requires at least one email address and one Import Id. If any user is missing those, the endpoint will fail and no user will be added to the operation.
2. Emails and Usernames will not be validated, but they must be unique or the user creation will fail.
3. If Roles are informed, they must be valid Rocket.Chat roles, or the endpoint will fail and no user will be added to the operation. 
4. The default roles will be added to all users automatically.
5. If no password is informed, a temporary random password will be generated automatically.
6. Users flagged as `deleted` will be created as Deactivated on Rocket.Chat.
7. Avatar Urls will not be fetched automatically. An admin needs to use the "Download Pending Avatars" button on the Admin/Import screen after the import is completed.
8. Import Ids will not be used as Ids by rocket.chat, but you can query users by their import id with the `users.info` endpoint.


## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/import.addUsers \
     -d '{"users": [{ "username": "john.doe", "emails": ["john.doe@example.com"], "importIds": ["1523"], "name": "John Doe", "password": "P@ssw0rd" }, { "username": "jane.doe", "emails": ["jane.doe@example.com"], "importIds": ["1524"], "name": "Jane Doe" }]}'
```

## Example Result

```javascript
{
   "success": true
}
```

## Change Log

| Version | Description                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------- |
| 6.3.0   | Added                                                                                              |
