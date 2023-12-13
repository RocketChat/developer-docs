# Set User Avatar

<table><thead><tr><th width="163">HTTP Method</th><th width="287">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.setAvatar</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `edit-other-user-avatar`, if the setting **AllowUserAvatarChange** is enabled.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="174">Key</th><th width="225">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>image</code><mark style="color:red;"><code>*</code></mark> or <code>avatarUrl</code><mark style="color:red;"><code>*</code></mark></td><td>Any image file or a URL <code>http://domain.tld/to/my/own/avatar.jpg</code></td><td><p>You have 2 options to set the user avatar:</p><ul><li>Upload the image file to use as the new avatar, as form data.</li><li>Enter the image URL you want to set as the user avatar.</li></ul></td></tr><tr><td><code>userId</code> or <code>username</code></td><td><code>BsNr28znDkG8aeo7W</code> or <code>bobsmith</code></td><td>The ID or username of the user. If not provided, the avatar of the user who is sending the request is updated.</td></tr></tbody></table>

## Example Call

With an image as form data:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -F "image=@my-own-avatar.png" \
     http://localhost:3000/api/v1/users.setAvatar
```

With URL:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     -d '{
          "avatarUrl": "http://domain.tld/to/my/own/avatar.jpg"}' \
     http://localhost:3000/api/v1/users.setAvatar
```

## Example Response

```json
{
    "success": true
}
```

## Change Log

<table><thead><tr><th width="308">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.56.0</td><td>Add support for <code>username</code> argument.</td></tr><tr><td>0.48.0</td><td>Set other users avatars if the callee has permission.</td></tr><tr><td>0.46.0</td><td>Added</td></tr></tbody></table>
