# Update a Team

Updates an existing team (name and type). Requires `edit-team` permission.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/teams.update` | `yes`         | `POST`      |

## Payload

| Argument | Example                                | Required | Description                                           |
| -------- | -------------------------------------- | -------- | ----------------------------------------------------- |
| `teamId` | `ByehQjC44FwMeiLbX`                    | Required | The team id.                                          |
| `data`   | `{ "name": "newTeamName", "type": 1 }` | Required | The new team name and type (0 - public, 1 - private). |

## Example Call

```bash
curl -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
     -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/teams.update \
     -d '{ "teamId": "ByehQjC44FwMeiLbX", "data": { "name": "newTeamName", "type": 1 }}'
```

## Example Result

```javascript
{
  "success": true
}
```
