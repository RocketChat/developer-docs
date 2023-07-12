# Get Team's Info

Gets a team's information. If the team is not public, the caller user must be a member of the team.

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `/api/v1/teams.info` | `yes`         | `GET`       |

## Query Parameters

| Argument            | Example                     | Required | Description                 |
| ------------------- | --------------------------- | -------- | --------------------------- |
| `teamId` `teamName` | `ByehQjC44FwMeiLbX` `team1` | Required | The team id. The team name. |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.info?teamName=Team1
```

## Example Result

```javascript
{
  "teamInfo": {
    "_id": "607e0d9b49d493189836bfac",
    "name": "Team1",
    "type": 1,
    "createdAt": "2021-04-19T23:09:15.106Z",
    "createdBy": {
      "_id": "FL2fZL4ERhwA3gWiS",
      "username": "some.username"
    },
    "_updatedAt": "2021-04-19T23:09:15.106Z",
    "roomId": "Dgh2xwJ3NFKWvKSqY"
  },
  "success": true
}
```

**Note:** `roomId` is the team's main room's id.
