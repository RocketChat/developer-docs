# Get Room Name By Id

Get room name by room id.

| Name              | Requires Auth | Permission    | Setting |
| ----------------- | ------------- | ------------- | ------- |
| `getRoomNameById` | Yes           | `view-c-room` |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example              | Required | Description  |
| -------- | -------------------- | -------- | ------------ |
| `rid`    | `siyr2oWQJBjQjhLwru` | Required | The room id. |

## Example call

```javascript
{
    "msg": "method",
    "method": "getRoomNameById",
    "id": "2",
    "params":[
        "siyr2oWQJBjQjhLwr"
    ]
   
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "2",
    "result": "try"
}
```
