---
description: Gets the banners to be shown to the authenticated user
---

# Get Banner

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/banners.getNew` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `platform` | `web` or `mobile` | true | The platform rendering the banner |
| `bid` | `ByehQjC44FwMeiLbX` | false | The `id` of a single banner |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/banners.getNew?platform=web&bid=ByehQjC44FwMeiLbX\
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
* **Missing Key**: Requires platform key for the request to be made.
* **Invalid Platform**: Requires a valid platform key for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing key \'platform\'" %}
```javascript
{
    "success": false,
    "error": "Match error: Missing key 'platform'"
}
```
{% endtab %}

{% tab title="Invalid Platform" %}
```javascript
{
    "success": false,
    "error": "Platform is unknown. [error-unknown-platform]",
    "errorType": "error-unknown-platform"
}
```
{% endtab %}
{% endtabs %}

