# Autocomplete Room Name for Private and Public Rooms

List the public and private rooms whose names match a given string, excluding [discussions](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/discussions), [DMs](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/direct-messages), and [omnichannel rooms](https://docs.rocket.chat/use-rocket.chat/omnichannel). The endpoint is valuable when performing search operations. It returns only rooms that the user belongs to.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.autocomplete.channelAndPrivate</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="203.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>selector</code><mark style="color:red;"><code>*</code></mark></td><td><code>{"name":"ran"}</code></td><td>The term to be completed. It only applies to room name.</td></tr></tbody></table>

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
            "_id": "664f0d525df46832f75b1860",
            "fname": "rancher",
            "name": "rancher",
            "t": "p"
        },
        {
            "_id": "6630e94ad2226209149c67e2",
            "fname": "random",
            "name": "random",
            "t": "c"
        },
        {
            "_id": "664f148f5df46832f75b18b2",
            "fname": "ranmowe",
            "name": "ranmowe",
            "t": "p"
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
