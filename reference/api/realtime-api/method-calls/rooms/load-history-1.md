# Add Room Leader

Set a user as room leader.

| Name            | Requires Auth | Permission   | Setting |
| --------------- | ------------- | ------------ | ------- |
| `addRoomLeader` | Yes           | `set-leader` |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                    | Required | Description                                  |
| -------- | -------------------------- | -------- | -------------------------------------------- |
| `roomId` | `64a1f373376181965ab77f54` | Required | The room id                                  |
| userId   | `5fRTXMt7DMJbpPJfh`        | Required | The id of the user to be set as room leader. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "addRoomLeader",
    "id": "2",
    "params": [
        "WDuJLFkjwk6L7LdFC",
        "5fRTXMt7DMJbpPJfh"
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
* **User is already a Leader**: This occurs when user is already a leader in that room.
* **No Permission:** This occurs when the authenticated user does not have the `set-leader` permission.

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
            "method": "addRoomLeader"
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
            "method": "addRoomLeader"
        },
        "message": "Invalid user [error-invalid-user]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="User is already a Leader" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-user-already-leader",
        "reason": "User is already a leader",
        "details": {
            "method": "addRoomLeader"
        },
        "message": "User is already a leader [error-user-already-leader]",
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
            "method": "addRoomLeader"
        },
        "message": "Not allowed [error-not-allowed]",
        "errorType": "Meteor.Error"
    }
}

```
{% endtab %}
{% endtabs %}
