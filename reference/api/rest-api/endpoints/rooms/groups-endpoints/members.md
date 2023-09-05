# Group Members

Lists the participants of a private group. It supports the [#pagination](../../../#pagination "mention") parameters.

Requires `view-broadcast-member-list` if room is a broadcast.

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `/api/v1/groups.members` | `yes`         | `GET`       |

## Query Parameters

| Argument            | Example                    | Required                   | Description                                                                                      |
| ------------------- | -------------------------- | -------------------------- | ------------------------------------------------------------------------------------------------ |
| `roomId`            | `ByehQjC44FwMeiLbX`        | Required(if no `roomName`) | The group's id                                                                                   |
| `roomName`          | `testChannel`              | Required(if no `roomId`)   | The group's name                                                                                 |
| `status`            | `['online', 'away']`       | Optional                   | The user's status (search filter).                                                               |
| `filter`            | `my-nickname`              | Optional                   | Extra search filters to be applied to the fields defined in the `Accounts_SearchFields` setting. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.members?roomId=ByehQjC44FwMeiLbX
```

## Example Result

```json
{
    "members": [
        {
            "_id": "Q4GkX6RMepGDdQ7YJ",
            "status": "online",
            "name": "Marcos Defendi",
            "utcOffset": -3,
            "username": "marcos.defendi"
        },
        {
            "_id": "rocket.cat",
            "name": "Rocket.Cat",
            "username": "rocket.cat",
            "status": "online",
            "utcOffset": 0
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
| 0.59.0  | Added       |
