# Check Username Availability

<figure><img src="../../../../.gitbook/assets/Deprecated.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This method is planned to be removed by 7.0.0. Use the `/users.checkUsernameAvailability` endpoint instead.
{% endhint %}

Confirm if a username is available.

| Name                        | Requires Auth |
| --------------------------- | ------------- |
| `checkUsernameAvailability` | Yes           |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

<table data-header-hidden><thead><tr><th width="161"></th><th width="161"></th><th width="166"></th><th></th></tr></thead><tbody><tr><td>Argument</td><td>Example</td><td>Required</td><td>Description</td></tr><tr><td><code>username</code></td><td><code>john.wood</code></td><td>Required</td><td>The username you are checking for.</td></tr></tbody></table>

## Example call

```javascript
{
    "msg": "method",
    "method": "checkUsernameAvailability",
    "id": "117",
    "params": [
        "funke"
    ]
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "117",
    "result": true
}
```
