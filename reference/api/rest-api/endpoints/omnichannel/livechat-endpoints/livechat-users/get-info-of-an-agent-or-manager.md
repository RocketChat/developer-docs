# Get an agent or manager

Get information about a particular agent or a manager.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/users/:type/:_id</code></td><td><code>yes</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="155.00000000000003">Key</th><th width="208">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr><tr><td><code>_id </code><mark style="color:red;"><code>*</code></mark></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The user <code>_id</code>.</td></tr></tbody></table>

## Example Call

{% swagger method="get" path="/api/v1/livechat/users/:type/:_id" baseUrl="http://localhost:3000" summary="Get information about an agent or a manager" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-parameter in="path" required="true" name="type" %}
Type of user
{% endswagger-parameter %}

{% swagger-parameter in="path" required="true" name="_id" %}
User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```json
{
  "user": {
    "_id": "SQafHvoFPuB57NmBD",
    "username": "john.doe",
    "name": "John Doe",
    "status": "offline",
    "statusLivechat": "available",
    "emails": [
    {
        "address": "john.doe@test.com",
        "verified": "true"
    }
    ],
    "livechat": {
        "maxNumberSimultaneousChat": ""
    }
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.42.0  | Added       |

##
