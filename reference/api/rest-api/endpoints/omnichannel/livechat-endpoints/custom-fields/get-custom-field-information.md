# Get Custom Field Information

Get details about a specific custom field.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/custom-fields/:_id</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Path Variables

<table><thead><tr><th width="197">Key</th><th width="254">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>address</code></td><td>The custom field ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/custom-fields/address
```

## Example Response

```json
{
    "customField": {
        "_id": "address",
        "label": "address",
        "scope": "visitor",
        "visibility": "visible",
        "regexp": "",
        "searchable": true,
        "type": "input",
        "required": false,
        "defaultValue": "",
        "options": "",
        "public": true,
        "_updatedAt": "2023-10-30T13:43:09.408Z",
        "id": "address"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
