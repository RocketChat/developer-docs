# List of teams of caller

Lists the public and private teams the caller is part of. It supports the [#pagination](../../../#pagination "mention") parameters.

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `/api/v1/teams.list` | `yes`         | `GET`       |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.list
```

## Example Result

```javascript
{
  "teams": [
    {
      "_id": "607e0d9b49d493189836bfac",
      "name": "team1",
      "type": 1,
      "createdAt": "2021-04-19T23:09:15.106Z",
      "createdBy": {
        "_id": "ew28FnZqipDpvKw3R",
        "username": "some.username"
      },
      "_updatedAt": "2021-04-19T23:09:15.106Z",
      "roomId": "Dgh2xwJ3NFKWvKSqY",
      "rooms": 2,
      "numberOfUsers": 2
    }
  ],
  "total": 1,
  "count": 1,
  "offset": 0,
  "success": true
}
```

**Note:** `roomId` is the team's main room's id.
