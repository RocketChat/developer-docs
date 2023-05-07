# Notify Room Stream

Use this call to notify a room about some specific events.

The method used is `stream-notify-room` and the general format is:

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

## Typing

One of the events you may notify a room about is the user typing on the keyboard. This call needs three params.

* `room-id/typing`: The first param is the room id followed with `/typing`
* `username`: The second param is the username
* `flag`: The third param is a boolean indicating if the user is typing \(`true`\) or it's not typing \(`false`\)

Example call \(the user is typing\):

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

One of the events you may notify a room about user activity like typing on the keyboard. This call needs four params.

* `room-id/user-activity`: The first param is the room id followed with `/user-activity`
* `username`: The second param is the username
* `events`: The third param is an array that contains all current user-activity like `["user-typing"]`
* `args`: The fourth param is the args dictionary

Example call \(the user is typing\):

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
