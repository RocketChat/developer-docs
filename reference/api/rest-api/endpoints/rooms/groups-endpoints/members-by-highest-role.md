# Group Members By Highest Role

Lists the participants of a group/channel sorted by their room-scoped roles.&#x20;

Room members are sorted by their most important role in the room. The following hierarchy is used: **Owner > Moderator > Other roles**. The information related to each user's highest role is returned in the `highestRole` object within each of them.

The `highestRole` object contains a numeric `level` field, which ranges from 0 to 2.&#x20;

* Level 0 stands for room owners.
* Level 1 is assigned to moderators (who are not room owners).
* Level 2 is assigned to all other team members regardless of their room-scoped roles.

The `highestRole` object also contains a `role` field, which has three possible values: `owner`, `moderator` or `member`, which are assigned to levels 0, 1, and 2, respectively.

Requires `view-broadcast-member-list` if the room is a broadcast.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.membersByHighestRole</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters.

<table><thead><tr><th width="197.33333333333331">Key</th><th width="230">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID. The parameter is required if <code>roomName</code> is not provided.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>testChannel</code></td><td>The group name. The parameter is required if <code>roomId</code> is not provided. </td></tr><tr><td><code>status</code></td><td><code>['online', 'away']</code></td><td>The user's status (search filter).</td></tr><tr><td><code>filter</code></td><td><code>my-nickname</code></td><td>Extra search filters to be applied to the fields defined in the <code>Accounts_SearchFields</code> setting.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.membersByHighestRole?roomId=ByehQjC44FwMeiLbX
```

## Example Response

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
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.5.0   | Added       |
