# Add Custom OAuth

Add custom OAuth service

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/settings.addCustomOAuth` | `Yes`         | `POST`      |

## Payload <a href="#payload" id="payload"></a>

| Argument | Example     | Required | Description            |
| -------- | ----------- | -------- | ---------------------- |
| `name`   | `New OAuth` | Required | The name of the Oauth. |

## Example Call

```
curl --location --request POST 'http://localhost:3000/api/v1/settings.addCustomOAuth' \
--header 'X-Auth-Token: eT9kwwdHSNJX5Sw7Ce_M0IcTuO5HOfDkyZwdXGfgAvy' \
--header 'X-User-Id: Dtx5kwoQJGYQSw3Qh' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "New OAuth"
}'
```

## Result

### Success

```json
{
    "success": true
}
```

### Errors

The following error can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Param not provided**: Occurs when the `name` parameter is not provided.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Param not Provided" %}
```json
{
    "success": false,
    "error": "The parameter \"name\" is required [error-name-param-not-provided]",
    "errorType": "error-name-param-not-provided"
}
```
{% endtab %}
{% endtabs %}
