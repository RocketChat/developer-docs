# Save Room Settings

| Name               | Requires Auth | Permission | Setting |
| ------------------ | ------------- | ---------- | ------- |
| `saveRoomSettings` | Yes           |            |         |

## Payload Parameters

| Argument | Example                    | Required | Description         |
| -------- | -------------------------- | -------- | ------------------- |
| `roomId` | _64a1f373376181965ab77f54_ | Required | The message object. |
| setting  | `joinCode`                 | Required |                     |

## &#x20;Available Settings

| Setting           | Accepted Values |
| ----------------- | --------------- |
| `roomName`        | String          |
| `roomTopic`       | String          |
| `roomDescription` | String          |
| `roomType`        | `c` or `p`      |
| `readOnly`        | Boolean         |
| `systemMessages`  | Boolean         |
| `default`         | Boolean         |
| `joinCode`        | String          |

## Example Call

```javascript
{
    "msg": "method",
    "method": "saveRoomSettings",
    "id": "1639",
    "params": [
        "64a1f373376181965ab77f54",
        "systemMessages",
        "false"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "1639",
    "result": {
        "result": true,
        "rid": "64a1f373376181965ab77f54"
    }
}
```
