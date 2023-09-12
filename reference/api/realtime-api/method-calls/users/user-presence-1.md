# Set User Password

| Name              | Requires Auth | Permission | Setting |
| ----------------- | ------------- | ---------- | ------- |
| `setUserPassword` | Yes           |            |         |

{% hint style="info" %}
The workspace administrator must enable the [**`Require password change`**](https://docs.rocket.chat/use-rocket.chat/workspace-administration/users#edit-a-user) field for the user. &#x20;
{% endhint %}

### Payload Parameters

| Argument   | Example   | Required | Description       |
| ---------- | --------- | -------- | ----------------- |
| `password` | `pass123` | Required | The new password. |

### Example Call

```javascript
{
    "msg": "method",
    "method": "setUserPassword",
    "id": "2",
    "params": [
      "pass123"
        
    ]
}
```

### Example Response

```javascript
{
    "msg": "result",
    "id": "2",
    "result": true
}
```



### Errors

* **Same password**: This occurs when the new **password** is same as the current password.
* **Not Allowed**: This occurs when the user does not have `Require password change` enabled.

{% tabs %}
{% tab title="Same password" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-password-same-as-current",
        "reason": "Entered password same as current password",
        "details": {
            "method": "setUserPassword"
        },
        "message": "Entered password same as current password [error-password-same-as-current]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}

{% tab title="Not allowed" %}
```json
{
    "msg": "result",
    "id": "2",
    "error": {
        "isClientSafe": true,
        "error": "error-not-allowed",
        "reason": "Not allowed",
        "details": {
            "method": "setUserPassword"
        },
        "message": "Not allowed [error-not-allowed]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}
