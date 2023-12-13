# Reset Avatar

<table><thead><tr><th width="163">HTTP Method</th><th width="287">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.resetAvatar</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required, if the setting **AllowUserAvatarChange** is enabled:&#x20;

* `edit-other-user-avatar`
* `manage-moderation-actions`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="212.33333333333331">Key</th><th width="232">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code></td><td>The ID or username of the user.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.resetAvatar \
     -d '{ 
          "userId": "BsNr28znDkG8aeo7W" }'
```

## Example Result

```json
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.55.0  | Added       |
