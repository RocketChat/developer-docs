# Autocomplete Room Name for Team

Autocompletes room name available for conversion to team

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.autocomplete.availableForTeams</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="169.33333333333331">Key</th><th width="267">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>data-loss-prevention</code></td><td>Name of the room.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl --location --request GET 'http://localhost:3000/api/v1/rooms.autocomplete.availableForTeams?name=data-loss-prevention\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

### Success

```json
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

The following error can occur:

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
