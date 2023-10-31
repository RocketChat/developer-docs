# Remove Agent or Manager

Remove a user as an agent or a manager.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/users/:type/:_id</code></td><td><code>yes</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="158">Key</th><th width="216">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr><tr><td><code>_id </code><mark style="color:red;"><code>*</code></mark></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The user <code>_id</code>.</td></tr></tbody></table>

## Example Call

{% swagger method="delete" path="/api/v1/livechat/users/:type/:_id" baseUrl="http://localhost:3000" summary="Remove an agent or manager" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-parameter in="path" name="type" required="true" %}
Type of user
{% endswagger-parameter %}

{% swagger-parameter in="path" name="_id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```javascript
{
  "success": true
}
```

## Change Log

<table><thead><tr><th width="298">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>
