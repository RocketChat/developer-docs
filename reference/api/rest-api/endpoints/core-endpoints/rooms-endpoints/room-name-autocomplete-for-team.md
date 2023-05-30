---
description: Autocompletes room name available for conversion to team
---

# Room name autocomplete for team

| URL                                           | Requires Auth | HTTP Method |
| --------------------------------------------- | ------------- | ----------- |
| `api/v1/rooms.autocomplete.availableForTeams` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument | Example                | Required | Description      |
| -------- | ---------------------- | -------- | ---------------- |
| name     | `data-loss-prevention` | Required | Name of the room |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/rooms.autocomplete.availableForTeams?name=data-loss-prevention\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "items": [
        {
            "_id": "osvTu9BnJuSiC8b8M",
            "name": "data-loss-prevention",
            "fname": "data-loss-prevention",
            "t": "p"
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
