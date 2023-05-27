---
description: Adds a new Server to search for public rooms later
---

# Add Server

| URL                                  | Requires Auth | HTTP Method |
| ------------------------------------ | ------------- | ----------- |
| `/api/v1/federation/addServerByUser` | `yes`         | `POST`      |

## Payload

<table><thead><tr><th width="225">Argument</th><th>Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>serverName</code></td><td><code>my-server.rocket.chat</code></td><td>Required</td><td>The public server name.</td></tr></tbody></table>

## Example payload

```javascript
{
  "serverName": "my-server.rocket.chat"
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/federation/addServerByUser \
    -d '{"serverName": "my-server.rocket.chat"}'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

<table><thead><tr><th>Version</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
