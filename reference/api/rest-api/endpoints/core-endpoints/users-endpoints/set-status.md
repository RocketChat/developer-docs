---
description: Sets a user Status when the status message and state is given.
---

# Set Status

| URL                       | Requires Auth | HTTP Method |
| ------------------------- | ------------- | ----------- |
| `/api/v1/users.setStatus` | `yes`         | `POST`      |

## Arguments

<table><thead><tr><th>Argument</th><th>Example</th><th width="121">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>message</code></td><td><code>My status update.</code></td><td>Required</td><td>The user's status message.</td></tr><tr><td><code>status</code></td><td><code>online</code></td><td>Optional</td><td>The user's status like <code>online</code>, <code>away</code>, <code>busy</code>, <code>offline</code>.</td></tr><tr><td><code>userId</code></td><td><code>zXuq7SvPKYbzYmfpo</code></td><td>Optional</td><td>The userId to change. The running user must have <code>edit-other-user-info</code> permission</td></tr><tr><td><code>username</code></td><td><code>rocket.cat</code></td><td>Optional</td><td>The username to change. The running user must have <code>edit-other-user-info</code> permission</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 40tB-Cn5YQJ74QMlQXi4Zf4E_-e0P5CrklU2pWOtV9M" \
     -H "X-User-Id: uunbZHiuEnib8Pawj" \
     -H "Content-type: application/json" \
     -d '{"message":"My status update", "status": "online"}' \
     http://localhost:3000/api/v1/users.setStatus
```

## Example Result

```javascript
{
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `1.2.0` | Added       |
