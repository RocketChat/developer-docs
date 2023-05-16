---
description: Removes a server
---

# Remove Server

| URL                                     | Requires Auth | HTTP Method |
| --------------------------------------- | ------------- | ----------- |
| `/api/v1/federation/removeServerByUser` | `yes`         | `POST`      |

## Payload

| Argument     | Example                 | Required | Description             |
| ------------ | ----------------------- | -------- | ----------------------- |
| `serverName` | `my-server.rocket.chat` | Required | The public server name. |

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
     http://localhost:3000/api/v1/federation/removeServerByUser\
    -d '{"serverName": "my-server.rocket.chat"}'
```

## Example Result

```javascript
{
  "success": true
}
```

<table><thead><tr><th>Version</th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
