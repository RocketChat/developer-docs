# Refresh OAuth Service

Resfresh the [OAuth services](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/oauth) in a workspace.

| Name              | Requires Auth | Permission          | Setting |
| ----------------- | ------------- | ------------------- | ------- |
| `addOAuthService` | Yes           | `add-oauth-service` | `None`  |

## Example call

```javascript
{
    "msg": "method",
    "method": "refreshOAuthService",
    "id": "44728"
}
```

## Example Response

### **Success**

```javascript
{
    "msg": "result",
    "id": "44728"
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
    "id": "44728",
    "error": {
        "isClientSafe": true,
        "error": "error-action-not-allowed",
        "reason": "Refresh OAuth Services is not allowed",
        "details": {
            "method": "refreshOAuthService",
            "action": "Refreshing_OAuth_Services"
        },
        "message": "Refresh OAuth Services is not allowed [error-action-not-allowed]",
        "errorType": "Meteor.Error"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.2  | Added       |
