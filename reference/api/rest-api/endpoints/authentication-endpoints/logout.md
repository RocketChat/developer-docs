# Logout

Invalidate your REST API authentication token.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/logout</code></td><td><a href="./"><code>yes</code></a></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST http://localhost:3000/api/v1/logout
```

## Example Response

```javascript
{
   "status": "success",
   "data": {
     "message": "You've been logged out!"
   }
}
```
