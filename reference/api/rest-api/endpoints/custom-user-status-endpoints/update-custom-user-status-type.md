---
description: Updates a custom user status
---

# Update custom user status type

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/custom-user-status.update` | `YES` | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/custom-user-status.update\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
 -d "_id=SeZHHb77QXWRbnDhn&name=Férias&statusType=busy"
```

## Result

### Success

```javascript
{
    "customUserStatus": {
        "_id": "SeZHHb77QXWRbnDhn",
        "name": "Férias",
        "statusType": "busy",
        "_updatedAt": "2021-09-26T15:23:46.325Z"
    },
    "success": true
}
```

### Errors

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No custom user status id**: Requires a valid custom user status `_id`

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="No custom user stauts id found" %}
```javascript
{
    "success": false,
    "error": "No custom user status found with the id of \"SeZHHb77QXWRbnDh\"."
}
```
{% endtab %}
{% endtabs %}

