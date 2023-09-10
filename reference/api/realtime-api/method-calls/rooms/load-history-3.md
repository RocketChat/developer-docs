# Add Room Owner

Set a user as room owner.

| Name           | Requires Auth | Permission  | Setting |
| -------------- | ------------- | ----------- | ------- |
| `addRoomOwner` | Yes           | `set-owner` |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example             | Required | Description                                 |
| -------- | ------------------- | -------- | ------------------------------------------- |
| `roomId` | `siyr2oWQJBjQjhLwr` | Required | The room id                                 |
| userId   | `5fRTXMt7DMJbpPJfh` | Required | The id of the user to be set as room owner. |

## Example Call

```javascript
{
    "msg": "method",
    "method": "addRoomOwner",
    "id": "2",
    "params": [
        "siyr2oWQJBjQjhLwr",
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
* **User is already a Owner**: This occurs when user is already a owner in that room.
* **No Permission:** This occurs when the authenticated user does not have the `set-owner` permission.

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
            "method": "addRoomOwner"
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
            "method": "addRoomOwner"
        },
        "message": "Invalid user [error-invalid-user]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="User is already an Owner" %}
````json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-user-already-owner",
        "reason": "User is already an owner",
        "details": {
            "method": "addRoomOwner"
        },
        "message": "User is already an owner [error-user-already-owner]",
        "errorType": "Meteor.Error"
    }
}
```
````
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
            "method": "addRoomOwner"
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
            "method": "addRoomOwner"
        },
        "message": "Invalid room [error-invalid-room]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}
