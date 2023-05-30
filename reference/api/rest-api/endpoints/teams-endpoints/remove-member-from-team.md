# Remove Member from Team

Removes a member from a team. Requires `edit-team-member` permission.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.removeMember` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `teamId`    `teamName` | `ByehQjC44FwMeiLbX`    `team1` | Required | The team id.    The team name. |
| `userId` | `ew28FnZqipDpvKw3R` | Required | The user id of who to remove from the team. |
| `rooms` | `["8dugqGhuRvCBLdZft"]` | Optional | The rooms \(ids\) from which the user should be removed. |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.removeMember \
      -d '{ "teamName": "team1", "userId": "kRwRRzfNybEDfQeij" }'
```

## Example Result

```javascript
{
  "success": true
}
```

