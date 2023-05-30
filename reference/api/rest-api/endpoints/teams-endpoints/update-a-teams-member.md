# Update a Team's Member

Updates a team member's roles. Requires `edit-team-member` permission.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.updateMember` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `teamId`    `teamName` | `ByehQjC44FwMeiLbX`    `team1` | Required | The team id.    The team name. |
| `member` | `{ "userId": "8dugqGhuRvCBLdZft", "roles": ["owner"] }` | Required | The user \(id and new roles\) to update in the team. |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.updateMember' \
      -d '{ "teamName": "team1", "member": { "userId": "LrTDRE27fWPEvaAwC", "roles": ["owner"] } }'
```

## Example Result

```javascript
{
  "success": true
}
```

