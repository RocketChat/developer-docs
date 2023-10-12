# Delete Room

Delete a room from the workspace.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/rooms.delete` | `yes`         | `POST`      |

## Payload

| Argument | Example                    | Required | Description   |
| -------- | -------------------------- | -------- | ------------- |
| `roomId` | `64adb09baa5ad4273bfc0cbf` | Required | The room's id |

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.delete' \
-H 'x-auth-token: Bln_vcvvbA9a9j2_GV0QdV52d-xoyLkNoOyPcD4cars' \
-H 'x-user-id: 5fRTXMt7DMJbpPJfh' \
-H 'Content-Type: application/json' \
-d '{
    "roomId":"64adb09baa5ad4273bfc0cbf"
}'
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
| 5.4.0   | Added       |
