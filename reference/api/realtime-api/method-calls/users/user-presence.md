# Set User Presence

Set the user presence status. By default, there are four different statuses available in your workspace:

* `online`
* `busy`
* `away`
* `offline`

## Setting Default User Presence Status

| Name                            | Requires Auth | Permission | Setting |
| ------------------------------- | ------------- | ---------- | ------- |
| `UserPresence:setDefaultStatus` | Yes           |            |         |

### Payload Parameters

| Argument | Example  | Required | Description                                    |
| -------- | -------- | -------- | ---------------------------------------------- |
| `status` | `online` | Required | The user presence status to be set as default. |

### Example Call

```javascript
{
    "msg": "method",
    "method": "UserPresence:setDefaultStatus",
    "id": "42",
    "params": [ "online" ]
}
```

### Example Response

```javascript
{
    "msg": "result",
    "id": "42",
    "result": true
}
```



## Setting Temporary User Presence Status

To set a temporary status, send a request to `UserPresence:{status}` with empty parameters. It only accepts either of these two status options: `away` and `online`. It is particularly useful when the client detects that the user is currently not actively using the application (thus "away") and when the user returns, indicating they are "online" again.

| Name                | Requires Auth | Permission | Setting |
| ------------------- | ------------- | ---------- | ------- |
| `UserPresence:away` | Yes           |            |         |

### Example Call

```javascript
{
    "msg": "method",
    "method": "UserPresence:away",
    "id": "47",
    "params":[]
}
```

### Example Response

```javascript
{
    "msg": "result",
    "id": "42",
    "result": true
}
```
