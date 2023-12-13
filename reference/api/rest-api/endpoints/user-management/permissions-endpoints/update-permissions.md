# Update Permissions

<table><thead><tr><th width="163">HTTP Method</th><th width="308">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/permissions.update</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `access-permissions`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="209.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>permissions</code><mark style="color:red;"><code>*</code></mark></td><td><code>[{"_id": "access-permissions", "roles": ["admin"]}]</code></td><td>The array of roles to overwrite.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/permissions.update \
     -d '{"permissions": [{"_id": "access-permissions", "roles": ["admin"]}]}'
```

## Example Response

```javascript
{
  "permissions": [
    {
      "_id": "access-permissions",
      "roles": [
        "admin"
      ],
      "_updatedAt": "2018-01-25T13:03:20.879Z",
      "meta": {
        "revision": 0,
        "created": 1516980515815,
        "version": 0
      },
      "$loki": 1
    },{
      ...
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.66.0  | Added.      |
