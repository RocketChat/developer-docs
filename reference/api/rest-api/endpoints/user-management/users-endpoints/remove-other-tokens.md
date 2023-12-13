# Remove Other Tokens

<table><thead><tr><th width="166">HTTP Method</th><th width="346">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.removeOtherTokens</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.removeOtherTokens \
```

## Example Response

```json
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.1.0   | Added       |
