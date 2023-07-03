# Archive Rooms

When a room is archived, it is designated as read-only and removed from the channel list on the left sidebar.

| Name          | Requires Auth | Permission     | Setting |
| ------------- | ------------- | -------------- | ------- |
| `archiveRoom` | Yes           | `archive-room` |         |

## Payload Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id |

## Example Call

```javascript
{
    "msg": "method",
    "method": "archiveRoom",
    "id": "3",
    "params": [
        "64a1f373376181965ab77f54"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "3"
}
```
