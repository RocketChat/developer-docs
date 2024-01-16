# Get List of Integrations

Requires at least one integration permission: `manage-incoming-integrations`, `manage-own-incoming-integrations`, `manage-outgoing-integrations` or `manage-own-outgoing-integrations`. It will return the integrations based on the user permissions.

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/integrations.list</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters, alongside the[#query-and-fields](../../../#query-and-fields "mention") parameters.

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.list
```

## Example Response

```json
{
    "integrations": [
        {
            "_id": "WMQDChpnYTRmFre9h",
            "enabled": true,
            "username": "rocket.cat",
            "alias": "Guggy",
            "avatar": "https://image.crisp.im/avatar/website/17651a90-e082-43f6-b308-957cea6e323c/128",
            "name": "Guggy",
            "triggerWords": [
                "!guggy",
                "guggy",
                "gif+"
            ],
            "urls": [
                "http://text2gif.guggy.com/guggify"
            ],
            "token": "aobEdbYhXfu5hkeqG",
            "script": ...,
            "scriptEnabled": true,
            "impersonateUser": false,
            "scriptCompiled": ...,
            "scriptError": null,
            "type": "webhook-outgoing",
            "userId": "rocket.cat",
            "channel": [],
            "_createdAt": "2017-01-05T17:06:05.660Z",
            "_createdBy": {
                "username": "graywolf336",
                "_id": "R4jgcQaQhvvK6K3iY"
            },
            "_updatedAt": "2017-01-05T17:06:05.660Z"
        },
        {
            "_id": "3aazpZ2WzoBP8msi9",
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
            "_createdAt": "2017-01-06T13:23:46.018Z",
            "_createdBy": {
                "username": "graywolf336",
                "_id": "R4jgcQaQhvvK6K3iY"
            },
            "_updatedAt": "2017-01-06T13:23:46.018Z"
        }
    ],
    "offset": 0,
    "items": 2,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description                                        |
| ------- | -------------------------------------------------- |
| 1.1.0   | Separate permissions in `incoming` and `outgoing`. |
| 0.49.0  | Added                                              |
