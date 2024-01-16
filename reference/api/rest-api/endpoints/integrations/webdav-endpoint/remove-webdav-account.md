# Remove WebDAV Account

Remove a specific WebDAV account

<table><thead><tr><th>URL</th><th width="200.33333333333331">Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/webdav.removeWebdavAccount</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td><td><code>GET</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="205">Key</th><th width="226.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>accountId</code><mark style="color:red;"><code>*</code></mark></td><td><code>P3Gru7ocFCd4vpKEs</code></td><td>The account ID that you want to remove.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/webdav.removeWebdavAccount
```

## Example Response

```json
{
  "success": true
}
```
