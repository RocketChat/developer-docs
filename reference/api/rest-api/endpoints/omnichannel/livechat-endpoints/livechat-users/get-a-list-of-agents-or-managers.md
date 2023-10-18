# Get a list of agents or managers

Get a list of agents or managers.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/users/:type</code></td><td><code>yes</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="167.00000000000003">Key</th><th width="162">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr></tbody></table>

## Query Parameters

The [#pagination](../../../../#pagination "mention") query parameters are supported and optional.

## Example Call

{% swagger method="get" path="/api/v1/livechat/users/:type" baseUrl="http://localhost:3000" summary="Get the details of all agents or managers" %}
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

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```javascript
{
  "users": [
    {
      "_id": "aobEdbYhXfu5hkeqG",
      "username": "john.doe"
    },
    {
      "_id": "SQafHvoFPuB57NmBD",
      "username": "doe.john"
    }
  ],
  "success": true
}
```

## Change Log

<table><thead><tr><th width="264">Version</th><th width="376">Description</th></tr></thead><tbody><tr><td>2.2.0</td><td>Added support to pagination</td></tr><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>

##
