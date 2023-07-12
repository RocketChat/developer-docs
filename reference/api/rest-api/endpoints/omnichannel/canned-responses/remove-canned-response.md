# Remove Canned Response

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Remove a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

{% hint style="info" %}
It requires the `remove-canned-responses`  [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `DELETE`    |

## Payload

| Argument | Example             | Required | Description               |
| -------- | ------------------- | -------- | ------------------------- |
| `_id`    | `EwmbZ9nLSx7kFamYB` | Required | The canned response's id. |

## Example payload

```json
{
    "_id": "646c7350a8c3a3ba32d0e2e0"
}

```

## Example Call

```bash
curl --location --request DELETE 'http://localhost:3000/api/v1/canned-responses' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-wXunBXi3j77OBY-T-gl1BvJ11jYiSMt6Z_G' \
--data '{
            "_id": "64700874a8c3a3ba32d0fb1c"
}'
```

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `logout-device-management` permission.
* **Canned Response not found:**  Occurs when the `_id` of the canned response does not exist.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Canned Response not found" %}
```json
{
    "success": false,
    "error": "Canned Response not found [error-canned-response-not-found]",
    "errorType": "error-canned-response-not-found",
    "details": {
        "method": "removeCannedResponse"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
