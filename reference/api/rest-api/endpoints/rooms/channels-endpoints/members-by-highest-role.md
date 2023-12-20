# Channel Members List By Highest Role

Lists all channel users sorted by their room scoped roles. It supports the [#pagination](../../../#pagination "mention") parameters.

Room members are sorted by their most important role in the room. The following hierarchy is used: **Owner > Moderator > Other roles**. The information related to each user's highest role is returned in the `highestRole` object within each of them.

The `highestRole` object contains a numeric `level` field which ranges from 0 to 2. Level 0 stands for room owners, while level 1 is assigned to moderators (that are not room owners) and level 2 is assigned to all other team members regardless of their room scoped roles.

The `highestRole` object also contains a `role` field, which has three possile values: `owner`, `moderator` or `member`, which are assigned to levels 0, 1 and 2, respectively.

{% hint style="info" %}
The list of elements a user can use to sort the list is limited. The current sortable element is:`username`
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.members</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

| Argument   | Example              | Required                  | Description                                                                                      |
| ---------- | -------------------- | ------------------------- | ------------------------------------------------------------------------------------------------ |
| `roomId`   | `ByehQjC44FwMeiLbX`  | Required (if no roomName) | The channel's id                                                                                 |
| `roomName` | `general`            | Required (if no roomId)   | The channel's name                                                                               |
| `status`   | `['online', 'away']` | Optional                  | The user's status (search filter).                                                               |
| `filter`   | `my-nickname`        | Optional                  | Extra search filters to be applied to the fields defined in the `Accounts_SearchFields` setting. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.membersByHighestRole?roomId=ByehQjC44FwMeiLbX&count=2
```

## Example Result

```json
{
    "members": [
        {
            "_id": "JmR3T4TFfppJCfmq9",
            "status": "offline",
            "_updatedAt": "2023-07-20T20:43:05.895Z",
            "name": "Matheus Barbosa Silva",
            "statusConnection": "offline",
            "username": "matheus.barbosa",
            "avatarETag": "fdJn5SqCwg4ZwbywD",
            "highestRole": {
              "role": "owner",
              "level": 0
            }
        },
        {
            "_id": "edjvbnb7pGC3MZNSP",
            "status": "offline",
            "_updatedAt": "2023-07-17T21:42:31.845Z",
            "username": "john",
            "name": "John",
            "statusConnection": "offline",
            "highestRole": {
              "role": "member",
              "level": 2
            }
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 35,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.5.0   | Added       |
