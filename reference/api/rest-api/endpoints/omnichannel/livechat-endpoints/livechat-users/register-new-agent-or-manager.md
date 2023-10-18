# Register new agent or manager

Register a new [agent](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) or [manager](https://docs.rocket.chat/use-rocket.chat/omnichannel/managers).

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/users/:type</code></td><td><code>yes</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="168">Key</th><th width="178.00000000000003">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user that you want to register. The value can either be <code>agent</code> or <code>manager</code>.</td></tr></tbody></table>

## Example Body

```json
{
  "username":"john.doe"
}
```

## Example Call

{% swagger method="post" path="/api/v1/livechat/users/:type" baseUrl="http://localhost:3000" summary="Register a user as an agent or a manager" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" required="true" %}
Username
{% endswagger-parameter %}

{% swagger-parameter in="path" name="type" required="true" %}
Type of user
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```javascript
{
  "user": {
    "_id": "SQafHvoFPuB57NmBD",
    "username": "john.doe"
  },
  "success": true
}
```

## Change Log

<table><thead><tr><th width="305">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>

##
