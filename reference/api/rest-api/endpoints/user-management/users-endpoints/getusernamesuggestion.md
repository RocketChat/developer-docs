# Get Username Suggestion

Gets a suggestion for a new username for the user.

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.getUsernameSuggestion</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getUsernameSuggestion
```

## Example Response

```json
{
  "result": "rocket.cat",
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.65.0  | Added       |
