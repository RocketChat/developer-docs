# Unmute User In a Room

Unmute a user in a room.

| Name               | Requires Auth | Permission  | Setting |
| ------------------ | ------------- | ----------- | ------- |
| `unmuteUserInRoom` | Yes           | `mute-user` |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                                                                                                   | Required | Description                                                          |
| -------- | --------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------- |
| `data`   | <pre><code>{
        "rid": "siyr2oWQJBjQjhLwr",
        "username": "test.funke"
        }
</code></pre> | Required | An object containing the room id and username of user to be unmuted. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "unmuteUserInRoom",
    "id": "2",
    "params": [
        {
        "rid": "siyr2oWQJBjQjhLwr",
        "username": "test.funke"
        }
    ]
}
```

## **Example Response**

### **Success**

```json
{
    "msg": "result",
    "id": "2",
    "result": true
}
```

### Errors

* **User not in the room**: This occurs when the `username` doesn't belong to any user in the room.
* **No Permission:** This occurs when the authenticated user does not have the `mute-user` permission.
* **Invalid Room**: This occurs when the `rid` is not a valid room id in the workspace.

{% tabs %}
{% tab title="User not in the room" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-user-not-in-room",
        "reason": "User is not in this room",
        "details": {
            "method": "unmuteUserInRoom"
        },
        "message": "User is not in this room [error-user-not-in-room]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-not-allowed",
        "reason": "Not allowed",
        "details": {
            "method": "unmuteUserInRoom"
        },
        "message": "Not allowed [error-not-allowed]",
        "errorType": "Meteor.Error"
    }
}

```
{% endtab %}

{% tab title="Invalid Room" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-invalid-room",
        "reason": "Invalid room",
        "details": {
            "method": "unmuteUserInRoom"
        },
        "message": "Invalid room [error-invalid-room]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}
