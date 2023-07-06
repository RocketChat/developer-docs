# stream-notify-user

Stream for a user.

## Events

* message
* otr (Off the Record Message)
* webrtc
* notification
* rooms-changed
* subscriptions-changed

## Example Call

```javascript
{
    "msg": "sub",
    "id": "unique-id",
    "name": "stream-notify-user",
    "params":[
        "user-id/webrtc",
        false
    ]
}
```
