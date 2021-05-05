# Members

Lists the public and private teams the caller is part of. It supports the [Offset, Count, and Sort Query Parameters](../../offset-and-count-and-sort-info.md).

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.members` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `teamId`    `teamName` | `ByehQjC44FwMeiLbX`    `team1` | Required | The team id.    The team name. |
| `name` | `Example Name` | Optional | The user's name \(search filter\). |
| `username` | `some.username` | Optional | The username \(search filter\). |
| `status` | `["online", "away", "busy"]` | Optional | The user's status \(search filter\). |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.members?teamName=team1&status[]=online&status=away&status=busy'
```

## Example Result

```javascript
{
  "members": [
    {
      "user": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username",
        "name": "Example Name",
        "status": "online"
      },
      "roles": [
        "owner"
      ],
      "createdBy": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username"
      },
      "createdAt": "2021-04-19T23:09:15.109Z"
    }
  ],
  "total": 3,
  "count": 1,
  "offset": 0,
  "success": true
}
```

