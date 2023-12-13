# Set User's Status Active

<table><thead><tr><th width="163">HTTP Method</th><th width="279">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.setActiveStatus</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `edit-other-user-active-status`
* `manage-moderation-actions`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="238">Key</th><th width="210">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>activeStatus</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>The value of the active status.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>5HmCfpoB7jp2uibTC</code></td><td>The user ID whose status value is to be changed.</td></tr><tr><td><code>confirmRelinquish</code></td><td><code>true</code></td><td>Allows the user to be deactivated even if it is the last owner of a room. By default, the value is <code>false.</code></td></tr></tbody></table>

{% hint style="info" %}
If `activeStatus=false` & `confirmRelinquish=true` and the user is the last remaining owner of a room, the oldest member of that room will be chosen as the new owner.
{% endhint %}

## Example call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.setActiveStatus \
     -d '{
          "activeStatus": false, 
          "userId": "5HmCfpoB7jp2uibTC"}'
```

## Example Response

```json
{
    "user": {
        "_id": "jJNyu4BQFqdgEcqnR",
        "active": false
    },
    "success": true
}
```

## Change Log

| Version | Description                               |
| ------- | ----------------------------------------- |
| 3.7.0   | Added `confirmRelinquish` to the payload. |
| 0.75.0  | Added.                                    |
