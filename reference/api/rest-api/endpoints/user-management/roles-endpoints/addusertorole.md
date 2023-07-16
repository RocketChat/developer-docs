# Role AddUserToRole

Assign a role to a user. Optionally, you can set this role to a room.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/roles.addUserToRole` | `yes`         | `POST`      |

## Payload

| Argument   | Example             | Required | Description                                                                                           |
| ---------- | ------------------- | -------- | ----------------------------------------------------------------------------------------------------- |
| `roleName` | `guest`             | Required | The role name.                                                                                        |
| `username` | `rocket.chat`       | Required | The user name.                                                                                        |
| `roomId`   | `dK7vNYXMdHGLdukpL` | Optional | If the role scope be Subscriptions and assign it to a room, you need to pass the roomId as parameter. |

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

## Example Result

```javascript
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
