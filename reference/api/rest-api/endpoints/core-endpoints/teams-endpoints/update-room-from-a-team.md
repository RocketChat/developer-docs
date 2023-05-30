# Update Room from a team

Updates a room from a team. Requires `edit-team-channel` permission.

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/teams.updateRoom` | `yes`         | `POST`      |

## Payload

| Argument    | Example             | Required | Description                                           |
| ----------- | ------------------- | -------- | ----------------------------------------------------- |
| `roomId`    | `Dgh2xwJ3NFKWvKSqY` | Required | The room id.                                          |
| `isDefault` | `true`              | Required | Sets the room as Auto-join (`true`) or not (`false`). |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.updateRoom \
      -d '{ "roomId": "8Z7eRsibvD5AANfmK", "isDefault": true }'
```

## Example Result

```javascript
{
  "room": {
    "_id": "8Z7eRsibvD5AANfmK",
    "name": "channelToUpdate",
    "fname": "channelToUpdate",
    "t": "c",
    "msgs": 7,
    "usersCount": 1,
    "u": {
      "_id": "FL2fZL4ERhwA3gWiS",
      "username": "some.username"
    },
    "customFields": {},
    "description": "",
    "broadcast": false,
    "encrypted": false,
    "ts": "2021-04-27T19:59:07.258Z",
    "ro": false,
    "_updatedAt": "2021-04-28T20:57:18.362Z",
    "teamId": "607e0d9b49d493189836bfac",
    "teamDefault": true
  },
  "success": true
}
```
