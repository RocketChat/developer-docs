---
description: REST API Favorite Methods
---

# Favorite/Unfavourite a Room

Favorite or unfavorite room.

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `/api/v1/rooms.favorite` | `yes`         | `POST`      |

## Payload

| Argument    | Example             | Required | Description                           |
| ----------- | ------------------- | -------- | ------------------------------------- |
| `roomId`    | `ByehQjC44FwMeiLbX` | Required | The room's id                         |
| `roomName`  | `general`           | Optional | The roomName                          |
| `favorite`  | `true`              | Required | A boolean to mark as favourite or not |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-Type: application/json" \
     http://localhost:3000/api/v1/rooms.favorite  \
     -d '{ "roomId": "GENERAL", "favorite": true }'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.64.0  | Added       |
