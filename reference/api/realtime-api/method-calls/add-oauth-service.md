# Add OAuth Service

Add an [OAuth service](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/oauth) for users to log in to your workspace.

{% hint style="info" %}
* It requires the `add-oauth-service` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| Name              | Requires Auth | Permission          | Setting |
| ----------------- | ------------- | ------------------- | ------- |
| `addOAuthService` | Yes           | `add-oauth-service` | `None`  |

## Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example | Required | Description                                    |
| -------- | ------- | -------- | ---------------------------------------------- |
| `name`   | `okta`  | Required | The name of the OAuth service you want to add. |

## Example call

```javascript
{
    "msg": "method",
    "method": "addOAuthService",
    "id": "2",
    "params": [
        "Okta"
    ]
}
```

## Example Response

### **Success**

```javascript
{
    "msg": "updated",
    "methods": [
        "2"
    ]
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
        "error": "error-action-not-allowed",
        "reason": "Adding OAuth Services is not allowed",
        "details": {
            "method": "addOAuthService",
            "action": "Adding_OAuth_Services"
        },
        "message": "Adding OAuth Services is not allowed [error-action-not-allowed]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.51.0  | Added       |
