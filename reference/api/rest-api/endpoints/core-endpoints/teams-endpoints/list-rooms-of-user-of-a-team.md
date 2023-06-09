# List Rooms Of User of a team

Lists only the team's rooms the user has joined. Requires `view-all-team-channels` permission. It supports the [Offset and Count Parameters](broken-reference).

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/teams.listRoomsOfUser` | `yes`         | `GET`       |

## Query Parameters

| Argument            | Example                     | Required | Description                                                                 |
| ------------------- | --------------------------- | -------- | --------------------------------------------------------------------------- |
| `teamId` `teamName` | `ByehQjC44FwMeiLbX` `team1` | Required | The team id. The team name.                                                 |
| `userId`            | `LrTDRE27fWPEvaAwC`         | Required | The user id (the endpoints returns the team channels this user has joined). |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.listRoomsOfUser?teamName=team1&userId=LrTDRE27fWPEvaAwC'
```

## Example Result

```javascript
{
  "rooms": [
    {
      "_id": "8Z7eRsibvD5AANfmK",
      "name": "someChannel",
      "fname": "someChannel",
      "t": "c",
      "msgs": 7,
      "usersCount": 1,
      "u": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username"
      },
      "customFields": {},
      "description": "",
      "broadcast": false,
      "encrypted": false,
      "ts": "2021-04-27T19:59:07.258Z",
      "ro": false,
      "_updatedAt": "2021-04-28T20:57:18.362Z",
      "teamId": "607e0d9b49d493189836bfac",
      "teamDefault": true,
      "isLastOwner": true
    }
  ],
  "total": 1,
  "count": 1,
  "offset": 0,
  "success": true
}
```
