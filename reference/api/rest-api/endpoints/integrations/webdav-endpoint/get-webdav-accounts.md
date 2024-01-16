# Get WebDAV Accounts

Retrieves the user's WebDAV accounts.

<table><thead><tr><th>URL</th><th width="200.33333333333331">Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/webdav.getMyAccounts</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td><td><code>GET</code></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/webdav.getMyAccounts
```

## Example Response

```json
{
  "accounts": [
    {
      "_id": "P3Gru7ocFCd4vpKEs",
      "server_url": "http://localhost:8080/remote.php/webdav/",
      "username": "admin",
      "name": "Webdav account"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
