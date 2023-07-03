# Save Room Settings

## Requirements

| Logged In | Permission  | Setting |
| --------- | ----------- | ------- |
| Yes       | `edit-room` | _none_  |

## Payload

1. String - the id of the room to leave
2. String - the room setting to save
3. Any - the value of the setting to save, this value type depends on what the setting accepts

## Available Settings

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
    "id": "16",
    "params": [
        "roomId",
        "setting",
        "value"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "16",
    "result": {
        "result": true,
        "rid": "roomId"
    }
}
```

## See Also

* [Create Channels](channels/create-channels.md)
* [Create Private Groups](create-private-groups.md)
* [Delete Rooms](rooms/delete-rooms.md)
* [Archive Rooms](rooms/archive-rooms.md)
* [Unarchive Rooms](rooms/unarchive-rooms.md)
