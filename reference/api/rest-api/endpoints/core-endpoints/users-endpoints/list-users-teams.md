---
description: Lists users teams
---

# List users teams

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/users.listTeams` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/users.listTeams\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d "userId=JxemcN9PDCdfzJe"
```

{% hint style="info" %}
If the caller has permission to view all teams, there's no need to filter the teams.
{% endhint %}

## Result

### Success

```javascript
{
    "teams": [
        {
            "_id": "612b8ae982d286c3",
            "name": "documentation-team",
            "type": 0,
            "createdAt": "2021-08-29T13:26:01.750Z",
            "createdBy": {
                "_id": "JxemcN9PDCdfzJe",
                "username": "renato.b"
            },
            "_updatedAt": "2021-08-29T13:26:01.762Z",
            "roomId": "GwktYAajqw4RiWiBK",
            "isOwner": true
        }
    ],
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

