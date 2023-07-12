# Remove a room from team

Removes a room from a team. Requires `remove-team-channel` permission.

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/teams.removeRoom` | `yes`         | `POST`      |

## Payload

| Argument            | Example                     | Required | Description                            |
| ------------------- | --------------------------- | -------- | -------------------------------------- |
| `teamId` `teamName` | `ByehQjC44FwMeiLbX` `team1` | Required | The team id. The team name.            |
| `roomId`            | `8Z7eRsibvD5AANfmK`         | Required | The room (id) to remove from the team. |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.removeRoom \
      -d '{ "teamName": "team1", "roomId": "8Z7eRsibvD5AANfmK" }'
```

## Example Result

```javascript
{
  "room": {
    "_id": "8Z7eRsibvD5AANfmK",
    "name": "roomRemovedFromTheTeam",
    "fname": "roomRemovedFromTheTeam",
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
    "_updatedAt": "2021-04-28T20:57:18.362Z"
  },
  "success": true
}
```
