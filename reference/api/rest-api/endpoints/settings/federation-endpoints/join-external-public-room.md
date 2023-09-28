---
description: Join an external public room
---

# Join external public room

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

| URL                                         | Requires Auth | HTTP Method |
| ------------------------------------------- | ------------- | ----------- |
| `/api/v1/federation/joinExternalPublicRoom` | `yes`         | `POST`      |

## Payload

<table><thead><tr><th width="225">Argument</th><th>Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>externalRoomId</code></td><td><code>!externalRoomId:server.com</code></td><td>Required</td><td>The external public room id.</td></tr></tbody></table>

## Example payload

```javascript
{
  "externalRoomId": "!externalRoomId:server.com"
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/federation/joinExternalPublicRoom \
    -d '{"externalRoomId": "!externalRoomId:server.com"}'
```

## Example Result

```javascript
{
  "success": true
}
```

<table><thead><tr><th>Version</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
