---
description: Creates custom user status
---

# Create custom user status

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `api/v1/custom-user-status.create` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## ayload

| Argument                            | Example  | Required | Description                                                                                             |
| ----------------------------------- | -------- | -------- | ------------------------------------------------------------------------------------------------------- |
| `name`                              | `vacay1` | Required | The name of the custom status.                                                                          |
| <pre><code>statusType
</code></pre> | `online` | Required | The `statusType` of the custom status. Valid status type includes: `Online`, `Busy`, `Away`, `Offline`. |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/custom-user-status.create' \
--header 'x-auth-token: Tkezshpjs9bi_kO09J4PcQM72UESdz9Dit6tT1uEzYMLnqzI' \
--header 'x-user-id: KDgshs2PcfJn8suegn69Mo' \
--header 'Content-Type: application/json' \
--data '{
    "name":"vacay1",
    "statusType":"online"
}'
```

## Result

### Success

```javascript
{
    "customUserStatus": {
        "_id": "EscbQinc8jmeXbpt7",
        "name": "In a meeting",
        "statusType": "Busy",
        "_updatedAt": "2021-09-26T14:03:43.057Z"
    },
    "success": true
}
```

### Errors

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Name pram empty**: Requires a custom user status `Name`.
* **The** **Status name** **already in use**: Requires a unique custom user status `Name`.
* **Invalid status type**: Requires a valid `StatusType` e.g. `Online` `Busy` `Away` `Offline`

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Name pram" %}
```javascript
{
    "success": false,
    "error": "The field Name is required [error-the-field-is-required]",
    "errorType": "error-the-field-is-required",
    "details": {
        "method": "insertOrUpdateUserStatus",
        "field": "Name"
    }
}
```
{% endtab %}

{% tab title="Status name already in use " %}
```javascript
{
    "success": false,
    "error": "The custom user status name is already in use [Custom_User_Status_Error_Name_Already_In_Use]",
    "errorType": "Custom_User_Status_Error_Name_Already_In_Use",
    "details": {
        "method": "insertOrUpdateUserStatus"
    }
}
```
{% endtab %}

{% tab title="Invalid status type" %}
```javascript
{
    "success": false,
    "error": "Offline is not a valid status type [error-input-is-not-a-valid-field]",
    "errorType": "error-input-is-not-a-valid-field",
    "details": {
        "method": "insertOrUpdateUserStatus",
        "input": "Offline",
        "field": "StatusType"
    }
}
```
{% endtab %}
{% endtabs %}
