# Visitor Autocomplete

Autocomplete a visitor's name.

<table><thead><tr><th width="163">HTTP Method</th><th width="329">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.autocomplete</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="219.33333333333331">Key</th><th width="269">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>selector</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "exceptions" : [], "conditions" : {"username": "guest-5"}}</code></td><td>Enter the exceptions or the conditions that you want to search for.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.autocomplete?selector={%20%22exceptions%22%3A%20[{}]%2C%20%22conditions%22%3A%20{%22username%22%3A%20%22guest-5%22}%20}' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5d' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "items": [
        {
            "_id": "6400be90fa0ed7dd90509300",
            "username": "guest-5",
            "name": "Jane",
            "custom_name": "guest-5 - An agent"
        }
    ],
    "success": true
}
```
