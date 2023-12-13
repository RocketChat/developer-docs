# Deactivate Idle Users

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.deactivateIdle</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `edit-other-user-active-status`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="223">Key</th><th width="184">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>daysIdle</code><mark style="color:red;"><code>*</code></mark></td><td><code>2</code></td><td>The number of days that the user is idle.</td></tr><tr><td><code>role</code></td><td><code>admin</code></td><td>The user role. By default, the value is <code>user</code>.</td></tr></tbody></table>

{% hint style="info" %}
The last login of the users is considered for deactivation. If no last login exists, then the date of creation is considered.
{% endhint %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.deactivateIdle \
     -d '{ 
          "daysIdle": 2, 
          "role": "admin" }'
```

## Example Response

```json
{
  "count": 1,
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.1.0   | Added       |
