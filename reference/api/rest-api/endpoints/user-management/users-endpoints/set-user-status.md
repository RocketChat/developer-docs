# Set User Status

<table><thead><tr><th width="163">HTTP Method</th><th width="279">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.setStatus</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `edit-other-user-info` and the setting **AllowUserStatusMessageChange** enabled.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="154">Key</th><th width="210">Example</th><th width="121">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>message</code></td><td><code>My status update.</code></td><td>Required</td><td>The user's status message.</td></tr><tr><td><code>status</code></td><td><code>online</code></td><td>Optional</td><td>The user's status like <code>online</code>, <code>away</code>, <code>busy</code>, <code>offline</code>.</td></tr><tr><td><code>userId</code></td><td><code>zXuq7SvPKYbzYmfpo</code></td><td>Optional</td><td>The userId to change. The running user must have <code>edit-other-user-info</code> permission</td></tr><tr><td><code>username</code></td><td><code>rocket.cat</code></td><td>Optional</td><td>The username to change. The running user must have <code>edit-other-user-info</code> permission</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 40tB-Cn5YQJ74QMlQXi4Zf4E_-e0P5CrklU2pWOtV9M" \
     -H "X-User-Id: uunbZHiuEnib8Pawj" \
     -H "Content-type: application/json" \
     -d '{"message":"My status update", "status": "online"}' \
     http://localhost:3000/api/v1/users.setStatus
```

## Example Response

```json
{
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `1.2.0` | Added       |
