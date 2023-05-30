# Delete a Team

Removes a team. Requires `delete-team` permission.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.delete` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `teamId`    `teamName` | `ByehQjC44FwMeiLbX`    `team1` | Required | The team id.    The team name. |
| `roomsToRemove` | `["8dugqGhuRvCBLdZft"]` | Optional | The rooms \(ids\) to delete along with team. |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.delete \
      -d '{ "teamId": "Isjsldk32sdkfA" }'
```

## Example Result

```javascript
{
  "success": true
}
```

