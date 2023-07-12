# Add federated server

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Add a new federated server. The [search-public-rooms.md](search-public-rooms.md "mention") endpoint will also return public rooms from this server.

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

### Success

```javascript
{
  "success": true
}
```

### Error&#x20;

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Already Added**: Occurs when the server has already been added.
* **Invalid Server Name**: This occurs when the server name is invalid.

{% tabs %}
{% tab title="Authorization" %}
```json
 {
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Already Added" %}
```json
{
    "success": false,
    "error": "already-a-default-server"
}
```
{% endtab %}

{% tab title="Invalid Server Name" %}
```json
{
    "success": false,
    "error": "invalid-server-name"
}
```
{% endtab %}
{% endtabs %}

## Change Log

<table><thead><tr><th>Version</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>
