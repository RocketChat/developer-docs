# Add Room Moderator

Set a user as room moderator.

| Name               | Requires Auth | Permission      | Setting |
| ------------------ | ------------- | --------------- | ------- |
| `addRoomModerator` | Yes           | `set-moderator` |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                    | Required | Description                                     |
| -------- | -------------------------- | -------- | ----------------------------------------------- |
| `roomId` | `64adb09baa5ad4273bfc0cbf` | Required | The room id                                     |
| userId   | `rbAXPnMktTFbNpwtJ`        | Required | The id of the user to be set as room moderator. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "addRoomModerator",
    "id": "2",
    "params": [
        "64adb09baa5ad4273bfc0cbf",
        "rbAXPnMktTFbNpwtJ"
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

* **User not in the room**: This occurs when the `userId` doesn't belong to any user in the room.
* **Invalid User**: This occurs when the `userId` doesn't belong to any user in the workspace.
* **User is already a Moderator**: This occurs when user is already a leader in that room.
* **No Permission:** This occurs when the authenticated user does not have the `set-moderator` permission.

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
            "method": "addRoomModerator"
        },
        "message": "User is not in this room [error-user-not-in-room]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="Invalid User" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-invalid-user",
        "reason": "Invalid user",
        "details": {
            "method": "addRoomModerator"
        },
        "message": "Invalid user [error-invalid-user]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="User is already a Moderator" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-user-already-moderator",
        "reason": "User is already a moderator",
        "details": {
            "method": "addRoomModerator"
        },
        "message": "User is already a moderator [error-user-already-moderator]",
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
            "method": "addRoomModerator"
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
            "method": "addRoomModerator"
        },
        "message": "Invalid room [error-invalid-room]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}
