# Get Integration History

Lists all history of the specified integration. Requires the permission `manage-outgoing-integrations` or `manage-own-outgoing-integrations`. It will return the integrations based on user permission.

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/integrations.history</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters, alongside the[#query-and-fields](../../../#query-and-fields "mention") parameters.

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.history?id=nvdQuJQ6tE9HRFBzd
```

## Example Response

```json
{
    "history": [],
    "offset": 0,
    "items": 0,
    "total": 0,
    "success": true
}
```

## Change Log

<table><thead><tr><th width="341">Version</th><th>Description</th></tr></thead><tbody><tr><td>1.1.0</td><td>Separate permissions in <code>incoming</code> and <code>outgoing</code>.</td></tr><tr><td>0.53.0</td><td>Added</td></tr></tbody></table>
