# Leave a Team

Causes the caller to be removed from the team.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.leave` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `teamId`    `teamName` | `ByehQjC44FwMeiLbX`    `team1` | Required | The team id.    The team name. |
| `rooms` | `["8dugqGhuRvCBLdZft"]` | Optional | The team rooms \(ids\) to remove the caller user from. |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.leave \
      -d '{ "teamName": "team1" }'
```

## Example Result

```javascript
{
  "success": true
}
```

