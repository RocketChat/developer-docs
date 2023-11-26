# Get Livechat Custom Fields

Get a list of the Livechat custom fields.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/custom-fields</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Query Parameters

This endpoint supports the [#pagination](../../../../#pagination "mention") query parameters.

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/custom-fields
```

## Example Response

```json
{
    "customFields": [
        {
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
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.2.0   | Added       |
