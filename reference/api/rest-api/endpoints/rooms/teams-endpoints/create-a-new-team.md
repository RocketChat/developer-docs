# Create a new Team

Creates a new team. Requires `create-team` permission.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/teams.create` | `yes`         | `POST`      |

## Payload

| Argument  | Example                 | Required | Description                                              |
| --------- | ----------------------- | -------- | -------------------------------------------------------- |
| `name`    | `TeamName`              | Required | The team name.                                           |
| `type`    | `0` or `1`              | Required | Privacy of the team (0 - Public, 1 - Private).           |
| `members` | `["8dugqGhuRvCBLdZft"]` | Optional | The user ids to add to the team when it is created.      |
| `room`    | `{ readOnly: true }`    | Optional | Additional options used to create the main team channel. |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.create \
      -d '{ "name": "teamName", "type": 0 }'
```

## Example Result

```javascript
{
  "team": {
    "_id": "608876e583314b02c8e6d857",
    "name": "teamName",
    "type": 0,
    "createdAt": "2021-04-27T20:41:09.738Z",
    "createdBy": {
      "_id": "FL2fZL4ERhwA3gWiS",
      "username": "some.username"
    },
    "_updatedAt": "2021-04-27T20:41:09.738Z",
    "roomId": "yv9KEJdTFjmerZprx"
  },
  "success": true
}
```

**Note:** `roomId` is the team's main room's id.
