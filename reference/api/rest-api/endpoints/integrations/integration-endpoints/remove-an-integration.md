# Remove an Integration

Removes an integration from the server. Requires `manage-incoming-integrations` or `manage-own-incoming-integrations` permissions to be able to remove incoming integrations and `manage-outgoing-integrations` or `manage-own-outgoing-integrations` to be able to remove outgoing integrations.

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/integrations.remove</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="213.33333333333331">Key</th><th width="222">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>webhook-outgoing</code></td><td>The type of integration to remove, <code>webhook-outgoing</code> and <code>webhook-incoming</code> are supported.</td></tr><tr><td><code>integrationId</code><mark style="color:red;"><code>*</code></mark></td><td><code>oNLthAt9RwMw39N2B</code></td><td>The ID of the integration to remove.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.remove \
     -d '{ 
          "type": "webhook-outgoing", 
          "integrationId": "oNLthAt9RwMw39N2B" }'
```

## Example Response

```json
{
    "integration": {
        "_id": "oNLthAt9RwMw39N2B",
        "type": "webhook-outgoing",
        "name": "Testing via REST API",
        "enabled": false,
        "username": "rocket.cat",
        "urls": [
            "http://text2gif.guggy.com/guggify"
        ],
        "scriptEnabled": false,
        "userId": "rocket.cat",
        "channel": [],
        "_createdAt": "2017-01-06T13:42:14.143Z",
        "_createdBy": {
            "username": "graywolf336",
            "_id": "R4jgcQaQhvvK6K3iY"
        },
        "_updatedAt": "2017-01-06T13:42:14.144Z"
    },
    "success": true
}
```

## Change Log

<table><thead><tr><th width="339">Version</th><th>Description</th></tr></thead><tbody><tr><td>1.1.0</td><td>Separate permissions in <code>incoming</code> and <code>outgoing</code>.</td></tr><tr><td>0.49.0</td><td>Added</td></tr></tbody></table>
