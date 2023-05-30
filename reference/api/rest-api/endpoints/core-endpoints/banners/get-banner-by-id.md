---
description: Gets the banner to be shown to the authenticated user
---

# Get banner by id

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `api/v1/banners/:id` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Params

| Argument   | Example | Required | Description                       |
| ---------- | ------- | -------- | --------------------------------- |
| `platform` | `web`   | true     | The platform rendering the banner |

## Path Variable

| Argument | Example             | Required | Description          |
| -------- | ------------------- | -------- | -------------------- |
| `id`     | `ByehQjC44FwMeiLbX` | true     | The id of the banner |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/banners/:id?platform=web\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "banners": [],
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing Key**: Requires `platform` key for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing key " %}
```javascript
{
    "success": false,
    "error": "Match error: Missing key 'platform'"
}
```
{% endtab %}
{% endtabs %}
