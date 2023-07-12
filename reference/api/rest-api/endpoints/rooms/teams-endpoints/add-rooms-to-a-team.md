# Add Rooms to a Team

Adds rooms to the team. Requires `add-team-channel` permission.

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `/api/v1/teams.addRooms` | `yes`         | `POST`      |

## Payload

| Argument            | Example                     | Required | Description                                   |
| ------------------- | --------------------------- | -------- | --------------------------------------------- |
| `teamId` `teamName` | `ByehQjC44FwMeiLbX` `team1` | Required | The team id. The team name.                   |
| `rooms`             | `["8dugqGhuRvCBLdZft"]`     | Required | The ids of the rooms to be added to the team. |

## Example Call

```bash
curl -H 'X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO' \
     -H 'X-User-Id: 8dugqGhuRvCBLdZft' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/teams.addRooms \
     -d '{ "teamId": "607e0d9b49d493189836bfac", "rooms": ["8Z7eRsibvD5AANfmK"]}'
```

## Example Result

```javascript
{
  "rooms": [
    {
      "_id": "8Z7eRsibvD5AANfmK",
      "name": "channelToAddToTeam",
      "fname": "channelToAddToTeam",
      "t": "c",
      "msgs": 0,
      "usersCount": 1,
      "u": {
        "_id": "8dugqGhuRvCBLdZft",
        "username": "some.username"
      },
      "customFields": {},
      "description": "",
      "broadcast": false,
      "encrypted": false,
      "ts": "2021-04-27T19:59:07.258Z",
      "ro": false,
      "_updatedAt": "2021-04-27T19:59:07.313Z",
      "teamId": "607e0d9b49d493189836bfac"
    }
  ],
  "success": true
}
```
