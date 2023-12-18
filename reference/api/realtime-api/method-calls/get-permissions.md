# Get Permissions

List all the [permissions](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions) in this workspace. Each permission is associated with a [role](https://docs.rocket.chat/setup-and-configure/roles-in-rocket.chat). You can use this information to customize your UI based on user permissions.

| Name              | Requires Auth | Permission | Setting |
| ----------------- | ------------- | ---------- | ------- |
| `permissions/get` | Yes           |            |         |

## Example Call

```javascript
{
    "msg": "method",
    "method": "permissions/get",
    "id": "423",
    "params": [
        {
            "_id": "8gMsLe9A7pZjo2D2iB",
            "rid": "64a1f373376181965ab77f54",
            "msg": "Hello World!"
        }
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "442",
    "result": [
        {
            "_id": "access-permissions",
            "_updatedAt": {
                "$date": 1688334885629
            },
            "roles": [
                "admin"
            ]
        },
        {
            "_id": "access-setting-permissions",
            "_updatedAt": {
                "$date": 1688334885660
            },
            "roles": [
                "admin"
            ]
        },
        {
            "_id": "add-oauth-service",
            "_updatedAt": {
                "$date": 1688334885667
            },
            "roles": [
                "admin"
            ]
        },
        {
            "_id": "add-user-to-joined-room",
            "_updatedAt": {
                "$date": 1688334885673
            },
            "roles": [
                "admin",
                "owner",
                "moderator"
            ]
        },
        {
            "_id": "add-user-to-any-c-room",
            "_updatedAt": {
                "$date": 1688334885682
            },
            "roles": [
                "admin"
            ]
        }
    }
       
```

## The Permission object

The permission object describes permission as:

* `_id`: The permission's id
* `roles`: A collection of roles that this permission applies to
* `_updatedAt`: (Optional) The last time this permission object was updated in the database
* `meta`: Metadata about the permission (described below)
* `$loki`: An internal property that can be ignored (it is removed on the web client before being added to the web client's database)
