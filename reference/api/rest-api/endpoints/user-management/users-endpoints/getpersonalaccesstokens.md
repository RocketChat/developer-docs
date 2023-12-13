# Get Personal Access Tokens

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.getPersonalAccessTokens</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `create-personal-access-tokens`
{% endhint %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.getPersonalAccessTokens
```

## Example Response

```json
{
  "tokens": [
        {
            "name": "myToken",
            "createdAt": "2018-08-01T17:17:48.068Z",
            "lastTokenPart": "R8Agh3"
        }
   ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.69.0  | Added       |
