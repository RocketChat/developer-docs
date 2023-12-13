# Update User

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.update</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* To save `customFields` you must first define the `customFields` in admin panel (Accounts -> Registration -> Custom fields)
* To update the password for the user, `edit-other-user-password` permission must be set using an administrator account (Administration > Permissions).
* This endpoint requires 2FA with your password. Refer to [#call-an-endpoint-with-2fa](../../authentication-endpoints/rest-two-factor-authentication.md#call-an-endpoint-with-2fa "mention")
{% endhint %}

## Body Parameters

<table><thead><tr><th width="220.33333333333331">Argument</th><th width="207">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code></td><td>The user ID to update.</td></tr><tr><td><code>data</code><mark style="color:red;"><code>*</code></mark></td><td><code>"data" : {}</code></td><td>The object that includes the user information to update with the following parameters.<br><strong>Note:</strong> If you provide an empty object, the user details are returned.</td></tr><tr><td><code>email</code></td><td><code>example@example.com</code></td><td>The email address for the user.</td></tr><tr><td><code>name</code></td><td><code>Example User</code></td><td>The display name of the user.</td></tr><tr><td><code>password</code></td><td><code>pass@w0rd</code></td><td>The password for the user.</td></tr><tr><td><code>username</code></td><td><code>example</code></td><td>The username for the user.</td></tr><tr><td><code>active</code></td><td><code>false</code></td><td>Whether the user is active, which determines if they can login or not.</td></tr><tr><td><code>roles</code></td><td><code>['bot']</code></td><td>The roles the user has been assigned.</td></tr><tr><td><code>joinDefaultChannels</code></td><td><code>false</code></td><td>Whether the user should join the default channels.</td></tr><tr><td><code>requirePasswordChange</code></td><td><code>true</code></td><td>Whether the user should be required to change their password when they login.</td></tr><tr><td><code>sendWelcomeEmail</code></td><td><code>true</code></td><td>Whether the user should get a welcome email.</td></tr><tr><td><code>verified</code></td><td><code>true</code></td><td>Whether the user's email address should be verified.</td></tr><tr><td><code>customFields</code></td><td><code>{ twitter: '@example' }</code></td><td>Any custom fields the user should have on their account.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.update \
     -d '{"userId": "BsNr28znDkG8aeo7W", 
          "data": { 
               "name": "new name", 
               "email": "newemail@user.tld" }}'
```

## Example Response

```json
{
   "user":{
      "_id": "BsNr28znDkG8aeo7W",
      "createdAt": "2016-09-13T14:57:56.037Z",
      "services": {
         "password": {
            "bcrypt": "$2a$10$5I5nUzqNEs8jKhi7BFS55uFYRf5TE4ErSUH8HymMNAbpMAvsOcl2C"
         }
      },
      "username": "uniqueusername",
      "emails": [
         {
            "address": "newemail@user.tld",
            "verified": false
         }
      ],
      "type": "user",
      "status": "offline",
      "active": true,
      "roles": [
         "user"
      ],
      "_updatedAt": "2016-09-13T14:57:56.175Z",
      "name": "new name",
      "customFields": {
         "twitter": "userstwitter"
      }
   },
   "success": true
}
```

## Change Log

| Version | Description               |
| ------- | ------------------------- |
| 0.48.0  | Renamed to `users.update` |
| 0.35.0  | Added as `user.update`    |
