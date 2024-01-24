# Close Chat

Close a chat session.

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| /api/apps/public/\{{app-id\}}/incoming | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>app-id</code></td><td><code>646b8e7d-f1e1-419e-9478-10d0f5bc74d9</code></td><td>Required</td><td>App id</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>action</code></td><td><code>close-chat</code></td><td>Required</td><td>The action</td></tr><tr><td><code>sessionId</code></td><td><pre><code>2Sfq8wXw4fYPMf6r4
</code></pre></td><td>Required</td><td>The id of the Rasa session</td></tr></tbody></table>

## Example Call

```javascript
curl "http://localhost:3000/api/apps/public/646b8e7d-f1e1-419e-9478-10d0f5bc74d9/incoming" \
-X POST \
-H "Content-Type: application/json" 
-d "  {
      "action": "close-chat",
      "sessionId": "2Sfq8wXw4fYPMf6r4"
  }" 
```

## Example Result

### Success

```json
 {
      "msg": " Close chat request handled successfully",

  }
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
