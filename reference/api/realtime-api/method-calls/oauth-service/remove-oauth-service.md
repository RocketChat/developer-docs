# Remove OAuth Service

Remove an [OAuth service](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/oauth).

| Name                 | Requires Auth | Permission          | Setting |
| -------------------- | ------------- | ------------------- | ------- |
| `removeOAuthService` | Yes           | `add-oauth-service` | `None`  |

## Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example | Required | Description                                       |
| -------- | ------- | -------- | ------------------------------------------------- |
| `name`   | `okta`  | Required | The name of the OAuth service you want to remove. |

## Example call

```javascript
{
    "msg": "method",
    "method": "removeOAuthService",
    "id": "2",
    "params": [
        "Zapier"
    ]
}
```

## Example Response

### **Success**

```javascript
{
    "msg": "result",
    "id": "2"
}
```

### Error

Any of the following errors can occur on the endpoint.

* **No Permission**: Occurs when the authenticated user doesn't have the `add-oauth-service` permission.

{% tabs %}
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
            "method": "removeOAuthService"
        },
        "message": "Not allowed [error-not-allowed]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}
