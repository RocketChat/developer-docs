---
description: Converts team to channel
---

# Convert team to channel

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/teams.convertToChannel` | `YES` | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/teams.convertToChannel\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name' \
-d "teamId=612b8ae982d286c3d1f5db31"
```

## Result

### Success

```javascript
{

    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing Team ID or Name**: Requires a valid Team ID or Name for the request to be made.
* **Invalid Team ID**: Requires a valid Team ID for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing Team ID or Name" %}
```javascript
{
    "success": false,
    "error": "missing-teamId-or-teamName"
}
```
{% endtab %}

{% tab title="Invalid Team ID" %}
```javascript
{
    "success": false,
    "error": "team-does-not-exist"
}
```
{% endtab %}
{% endtabs %}

