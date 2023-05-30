---
description: List the user whose names match a given pattern.
---

# Autocomplete User

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/users.autocomplete` | `yes` | `GET` |

## Parameters

| Argument | Example | Required |
| :--- | :--- | :--- |
| `selector` | `{ "exceptions" : []}` | Required |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/users.autocomplete'
```

## Result

### Success

```javascript
{
    "items": [
        {
            "_id": "6esQ6cpqSQYvoLTvC",
            "username": "Aaron.altamirano",
            "status": "offline",
            "name": "Aaron Altamirano ",
            "nickname": "aaron.altamirano@rocket.chat"
        },
        {
            "_id": "AySWYsyzToxy3239z",
            "username": "Balazs.Nemethi",
            "status": "offline",
            "name": "Balázs Némethi"
        },
        {
            "_id": "gxcJTYapi5mPxuAme",
            "username": "Bruno.Solis",
            "status": "offline",
            "name": "Bruno Solis",
            "avatarETag": "ZAHMxLQ6bW426Knwm"
        },
        {
            "_id": "kvqbntLso8y2dEx7C",
            "username": "Ivan.Belousov",
            "status": "offline",
            "name": "Ivan"
        },
        {
            "_id": "AkFjhgJFHAhNK3e6o",
            "status": "offline",
            "name": "Karina Monarkh",
            "username": "Karina"
        },
        {
            "_id": "M3ajjGeyg8SfKXopd",
            "username": "Rucks_guest2",
            "status": "offline",
            "name": "Rucks_guest2",
            "nickname": "anonymous3"
        }
    ],
    "success": true
}
```

### Errors <a id="errors"></a>

The following error can occur upon the endpoint.‌

* **Authorization**: Requires an authentication token for the request to be made.
* **Selector Param**: Requires selector param for the request to be made.

{% tabs %}
{% tab title="Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Selector Param " %}
```javascript
{
    "success": false,
    "error": "The 'selector' param is required"
}
```
{% endtab %}
{% endtabs %}

