# Delete

Remove a direct message session.

N.B. this endpoint requires the authenticated user to have the `view-room-administration` permission.

| URL                 | Requires Auth | HTTP Method |
| ------------------- | ------------- | ----------- |
| `/api/v1/im.delete` | `yes`         | `POST`      |

## Payload

| Argument   | Example             | Required                  | Description                                          |
| ---------- | ------------------- | ------------------------- | ---------------------------------------------------- |
| `username` | `rocket.cat`        | Required (if no roomId)   | The username of the other direct message participant |
| `roomId`   | `ByehQjC44FwMeiLbX` | Required (if no username) | The direct message session id                        |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/im.delete \
     -d '{ "roomId": "ByehQjC44FwMeiLbX" }'
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
| 3.18.0  | Added       |
