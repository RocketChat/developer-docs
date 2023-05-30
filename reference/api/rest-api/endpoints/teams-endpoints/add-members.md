---
description: Adds members to the team.
---

# Add Members to Team

Requires `add-team-member` or `edit-team-member` permissions.

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/teams.addMembers` | `yes`         | `POST`      |

## Payload

| Argument            | Example                                                    | Required | Description                                   |
| ------------------- | ---------------------------------------------------------- | -------- | --------------------------------------------- |
| `teamId` `teamName` | `ByehQjC44FwMeiLbX` `team1`                                | Required | The team id. The team name.                   |
| `members`           | `[{ "userId": "8dugqGhuRvCBLdZft", "roles": ["member"] }]` | Required | The users (ids and roles) to add to the team. |

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.addmembers \
      -d '{ "teamId": "Isjsldk32sdkfA", "members": [{ "userId": "aobEdbYhXfu5hkeqG", "roles": ["owner"]}] }'
```

## Example Result

```javascript
{
  "success": true
}
```
