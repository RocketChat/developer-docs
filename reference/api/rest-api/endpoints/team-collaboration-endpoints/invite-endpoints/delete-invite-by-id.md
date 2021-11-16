---
description: Deletes an invite from the server.
---

# Delete invite by id

{% hint style="info" %}
Requires the `create-invite-links `permission.
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `api/v1/removeInvite/:_id` | `YES`         | `DELETE`    |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Payload

| Argument | Example    | Required | Description                         |
| -------- | ---------- | -------- | ----------------------------------- |
| `_id`    | `'kDKQ3H'` | Required | The id of the invite to be deleted. |

## Example Call

```bash
curl --location --request DELETE 'http://localhost:3000/api/v1/removeInvite/:_id\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
 -d "customUserStatusId=EscbQinc8jmeXbpt7"
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Errors

Any of the following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Invitation Id**: Requires a valid invitation  `_id`

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```


{% endtab %}

{% tab title="Invalid Invitation Id" %}
```javascript
{
    "success": false,
    "error": "Invalid Invitation _id [invalid-invitation-id]",
    "errorType": "invalid-invitation-id",
    "details": {
        "method": "removeInvite"
    }
}
```


{% endtab %}
{% endtabs %}
