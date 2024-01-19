# Get your E2E Keys

Retrieves E2E keys of logged-in user.

| URL                      | Requires Auth                            | HTTP Method |
| ------------------------ | ---------------------------------------- | ----------- |
| `api/v1/e2e.fetchMyKeys` | [`YES`](../../authentication-endpoints/) | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                            |
| -------------- | -------------- | -------- | ------------------------------------------------------ |
| `X-User-Id`    | `myuser-id`    | Required | User Id retuned from api login.                        |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/e2e.fetchMyKeys\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myumser-id'
```

## Example Response

### Success

{% code overflow="wrap" %}
```json
{
    "public_key": "{\"alg\":\"RSA-OAEP-256\",\"e\":\"AQAB\",\"ext\":true,\"key_ops\":[\"encrypt\"],\"kty\":\"RSA\",\"n\":\"oP23XEagSGIdo18Yc7TUwsM1qoRDa-pMg64lEctMQ6Dx-Q\"}",
    "private_key": "{\"$binary\":\"2j5AaYO39PcQNK7lT3h5Zv7j7y3rVKsqlERVgty+Z2pjzuG5pCMnx63WFJCrt8Sx2KDwWvYycGs0V5TzXJhKFEpE3l5hpoP51wO1Xztnfl9TdVtCZ5ERSDhXp+t3ays0QLdD2EtZu9M+Ffgiy2gqTasB0UFXAZyDA==\"}",
    "success": true
}
```
{% endcode %}

### Error

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}
{% endtabs %}
