# List All Teams with Info

Lists all of the teams and their information. Requires `view-all-teams` permission. It supports the [Offset and Count Parameters](../other-important-endpoints/offset-and-count-and-sort-info.md).

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/teams.listAll` | `yes`         | `GET`       |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.listAll
```

## Example Result

```javascript
{
  "teams": [
    {
        "_id": "Isjsldk32sdkfA",
        "name": "team1",
        "type": 0,
        "createdAt": "2016-05-30T13:42:25.304Z"
        "createdBy": {
           "_id": "aobEdbYhXfu5hkeqG",
           "username": "some.username"
        },
        "_updatedAt": "2020-05-21T13:14:07.096Z",
        "roomId": "Dgh2xwJ3NFKWvKSqY",
        "rooms": 2,
        "numberOfUsers": 2
    },
    {
        "_id": "asdf97xcv87",
        "name": "team2",
        "type": 1,
        "createdAt": "2016-05-30T13:42:25.304Z"
        "createdBy": {
           "_id": "aobEdbYhXfu5hkeqG",
           "username": "example"
        },
        "_updatedAt": "2020-05-21T13:14:07.096Z",
        "roomId": "Fda3TghyU03WqsYEv",
        "rooms": 5,
        "numberOfUsers": 4
    }
  ],
  "total": 2,
  "count": 2,
  "offset": 0,
  "success": true
}
```

**Note:** `roomId` is the team's main room's id.
