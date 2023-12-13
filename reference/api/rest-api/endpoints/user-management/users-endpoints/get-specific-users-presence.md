# Get Specific User's Presence

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.getPresence</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="208.33333333333331">Key</th><th width="228">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code> or <code>test</code></td><td><p>The ID or username of the user. </p><p>If not provided, the user who sending the request is retrieved.</p></td></tr></tbody></table>

## Example Call

With `userId`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getPresence?userId=BsNr28znDkG8aeo7W
```

With `username`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getPresence?username=test
```

With no query parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getPresence
```

## Example Response

```javascript
{
  "presence": "offline",
  "success": true
}
```

## Change Log

| Version | Description                               |
| ------- | ----------------------------------------- |
| 0.49.0  | Updated to support `userId` or `username` |
| 0.48.0  | Renamed to `users.getPresence`            |
| 0.35.0  | Added as `user.getPresence`               |
