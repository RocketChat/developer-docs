# Autocomplete private channel

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/rooms.autocomplete.channelAndPrivate` | `yes` | `GET` |

## Parameters

| Argument | Example | Required |
| :--- | :--- | :--- |
| `selector` | `{ "exceptions" : []}` | Required |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/rooms.autocomplete.channelAndPrivate?selector=[]\
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
        },
        {
            "_id": "H3Li6yWc5tz2hbvmu",
            "name": "demo-channel-12-11",
            "fname": "demo-channel-12-11",
            "t": "p"
        },
        {
            "_id": "ThS4AKxCgBfv5xqQD",
            "fname": "Omnichannel Facebook Setup",
            "name": "omnichannel-facebook-setup",
            "t": "c"
        },
        {
            "_id": "phqYWtZZrGWrEZWue",
            "fname": "Omnichannel Instagram Setup",
            "name": "omnichannel-instagram-setup",
            "t": "p"
        },
        {
            "_id": "ZhB63qsrJMQ7k3RYx",
            "fname": "Omnichannel Twitter Setup",
            "name": "omnichannel-twitter-setup",
            "t": "p"
        },
        {
            "_id": "umr9xvCpqCBtsjYkE",
            "fname": "Omnichannel WhatsApp Setup",
            "name": "omnichannel-whatsapp-setup",
            "t": "c"
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

{% tab title="Selector Param" %}
```javascript
{
    "success": false,
    "error": "The 'selector' param is required"
}
```
{% endtab %}
{% endtabs %}

