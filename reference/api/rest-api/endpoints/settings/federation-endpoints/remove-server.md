---
description: Removes a server
---

# Remove federated server

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="200">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/federation/removeServerByUser</code></td><td><code>yes</code></td><td><code>POST</code></td></tr></tbody></table>

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

### Success

```javascript
{
  "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Can't remove default server**: This occurs when trying to remove a default server.

{% tabs %}
{% tab title="Authorization" %}
```json
 {
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Can't remove default server" %}
```json
{
    "success": false,
    "error": "cannot-remove-default-server"
}
```
{% endtab %}
{% endtabs %}

<table><thead><tr><th>Version</th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
