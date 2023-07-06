# Notify Room Stream

Notify a room about some specific events.

## Events

* Typing
* user-activity

## Example Call

```javascript
{
    "msg": "method",
    "method": "stream-notify-room",
    "id": "42",
    "params": [
        ... // params varies
    ]
}
```

### Typing

You can notify a room about a user typing on the keyboard.

#### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument         | Example                           | Required | Description                                                                        |
| ---------------- | --------------------------------- | -------- | ---------------------------------------------------------------------------------- |
| `room-id/typing` | `64a1f373376181965ab77f54/typing` | Required | The room id follwed by `/typing`                                                   |
| `username`       | `testrc`                          | Required | The username                                                                       |
| `flag`           | `true`                            | Required |  A boolean indicating if the user is typing (`true`) or it's not typing (`false`). |

```javascript
{
    "msg": "method",
    "method": "stream-notify-room",
    "id": "42",
    "params": [
        "room-id/typing",
        "username",
        true
    ]
}
```

## user-activity

You can notify a room about user activity like typing on the keyboard.

#### Payload Parameters

| Argument                | Example                           | Required | Description                                                                        |
| ----------------------- | --------------------------------- | -------- | ---------------------------------------------------------------------------------- |
| `room-id/user-activity` | `64a1f373376181965ab77f54/typing` | Required | The room id follwed by `/user-activity`                                            |
| `username`              | `testrc`                          | Required | The username                                                                       |
| `events`                | `["user-typing"]`                 | Required |  A boolean indicating if the user is typing (`true`) or it's not typing (`false`). |
| `args`                  | {}                                |          |                                                                                    |

Example call (the user is typing):

```javascript
{
    "msg": "method",
    "method": "stream-notify-room",
    "id": "42",
    "params": [
        "room-id/user-activity",
        "username",
        ["user-typing"],
        {}
    ]
}
```
