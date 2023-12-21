# Autocomplete Private Channel

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.autocomplete.channelAndPrivate</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="203.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>selector</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "exceptions" : []}</code></td><td>Provide additional values to filter the results.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl --location --request GET 'http://localhost:3000/api/v1/rooms.autocomplete.channelAndPrivate?selector=[]\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

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

### Errors <a href="#errors" id="errors"></a>

The following errors can occur:

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
