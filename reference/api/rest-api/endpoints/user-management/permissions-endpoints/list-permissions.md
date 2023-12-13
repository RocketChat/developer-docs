# List Permissions

<table><thead><tr><th width="163">HTTP Method</th><th width="308">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/permissions.listAll</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="194.33333333333331">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>updatedSince</code></td><td><code>2017-11-25T15:08:17.248Z</code></td><td>Date as ISO string.<br>If you include this parameter, the <code>update</code> and <code>remove</code> fields in the response will contain only those permissions updated and removed since this date and time.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/permissions.listAll?updatedSince=2017-11-25T15:08:17.248Z
```
{% endcode %}

## Example Response

```json
{
  "update": [
    {
       "_id": "access-permissions",
       "_updatedAt": "2018-11-28T11:55:49.106Z",
       "roles": [
           "admin"
       ]
    },
    {
        "_id": "add-oauth-service",
        "_updatedAt": "2018-11-28T12:59:51.974Z",
        "roles": [
           "admin",
           "user"
         ]
   }
  ],
  "remove": [],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.73.0  | Added       |
