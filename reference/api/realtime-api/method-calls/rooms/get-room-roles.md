# Get Room Roles

Get a collection of users and their roles per room. You can send a collection of room ids (at least one).

The user roles per room object is defined as:

* `rid`: The room id this user and role belongs to
* `u`: A simple user object with the user id and username
* `roles`: The collection of roles of the user in the room
* `_id`: the id of this object

## Example Call

```javascript
{
    "msg": "method",
    "method": "getRoomRoles",
    "id": "42",
    "params": [ "room-id" ]
}
```

## Example Response&#x20;

```javascript
{
    "msg": "result",
    "id": "42",
    "result": [
        {
            "rid": "room-id",
            "u": { "_id": "user-id", "username": "username" },
            "roles": [ "role-name" ],
            "_id": "id"
        }
    ]
}
```
