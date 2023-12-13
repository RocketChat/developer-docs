# Get Updated Roles

Gets all the roles in the system, which are updated after a given date.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/roles.sync</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="234.33333333333331">Key</th><th width="232">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>updatedSince</code><mark style="color:red;"><code>*</code></mark></td><td><code>2017-11-25T15:08:17.248Z</code></td><td>Date as ISO string.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.sync?updatedSince=2017-11-25T15:08:17.248Z
```

## Example Response

```json
{
  "roles": {
   "update" :[
      {
        "_id": "admin",
        "description": "Admin",
        "mandatory2fa": false,
        "protected": true,
        "scope": "Users"
      }
    ],
    "remove" : [
      {
        "_id": "user",
        "description": "User",
        "mandatory2fa": false,
        "protected": true,
        "scope": "Users"
      }
    ]
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.1.0   | Added       |
