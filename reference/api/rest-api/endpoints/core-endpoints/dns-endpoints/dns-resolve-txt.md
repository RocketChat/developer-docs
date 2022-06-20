---
description: Resolves DNS text records (TXT records) for a hostname
---

# DNS Resolve txt



| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `api/v1/dns.resolve.txt` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Params

| Argument | Example          | Required | Description  |
| -------- | ---------------- | -------- | ------------ |
| `url`    | `localhost:3000` | true     | The hostname |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/dns.resolve.txt?url=open.rocket.chat\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Hostname**: Requires a valid hostname for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```


{% endtab %}

{% tab title="Invalid Hostname" %}
```javascript
{
    "success": false,
    "error": "querySrv ENOTFOUND .rocket.chat/"
}
```
{% endtab %}
{% endtabs %}
