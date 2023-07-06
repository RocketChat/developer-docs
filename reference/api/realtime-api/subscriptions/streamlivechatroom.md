# stream-room-messages

Stream room messages.

## Payload Parameters

| Argument             | Example                    | Required | Description                        |
| -------------------- | -------------------------- | -------- | ---------------------------------- |
| `roomId`             | `64a1f373376181965ab77f54` | Required | The room id                        |
| `back-compatibility` | `false`                    | Required | Boolean to set back-compatibility. |

## Example Call

```javascript

{
    "msg": "sub",
    "id": "89494",
    "name": "stream-room-messages",
    "params":[
        "64a1f373376181965ab77f54",
        false
    ]
}

```

## Example Response

```javascript
{
    "msg":"ready",
    "subs":[
        "89494"
    ]
}
```
