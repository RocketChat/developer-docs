---
description: List the teams whose names match a given pattern.
---

# Autocomplete Team

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/teams.autocomplete` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `name` | `team` | Required | The pattern \(search filter for team names\). |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.autocomplete?name=team'
```

## Example Result

```javascript
{
  "teams": [
    {
      "_id": "Dgh2xwJ3NFKWvKSqY",
      "name": "team1",
      "fname": "team1",
      "t": "p",
      "teamId": "607e0d9b49d493189836bfac"
    }
  ],
  "success": true
}
```



