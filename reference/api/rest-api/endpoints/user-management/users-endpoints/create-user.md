# Create User

Create a new workspace user.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `create-user`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="267">Key</th><th width="208">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>example@example.com</code></td><td>The email address for the user.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Example User</code></td><td>The display name of the user.</td></tr><tr><td><code>password</code><mark style="color:red;"><code>*</code></mark></td><td><code>pass@w0rd</code></td><td>The password for the user.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>example</code></td><td>The username for the user.</td></tr><tr><td><code>active</code></td><td><code>false</code></td><td>Whether the user is active, which determines if they can login or not.<br>By default, the value is <code>true</code>.</td></tr><tr><td><code>bio</code></td><td><code>Enginer|GitHub Star</code></td><td>The bio of the user.</td></tr><tr><td><code>nickname</code></td><td><code>lola</code></td><td>The nickname of the user.</td></tr><tr><td><code>statusText</code></td><td><code>On a vacation</code></td><td>The status text of the user.</td></tr><tr><td><code>roles</code></td><td><code>["bot"]</code></td><td>The roles the user is assigned on creation. The default value is <code>user</code>.</td></tr><tr><td><code>joinDefaultChannels</code></td><td><code>false</code></td><td>Whether the user should join the default channels when created. The default value is <code>true</code>.</td></tr><tr><td><code>requirePasswordChange</code></td><td><code>true</code></td><td>Whether the user be required to change their password when they login. The default value is <code>false</code>.</td></tr><tr><td><code>setRandomPassword</code></td><td><code>true</code></td><td>Set random password for the user and send by email. If <code>setRandomPassword</code> is set to <code>true</code>, the password field can be left empty.</td></tr><tr><td><code>sendWelcomeEmail</code></td><td><code>true</code></td><td>Whether the user get a welcome email. The default value is <code>false</code>.</td></tr><tr><td><code>verified</code></td><td><code>true</code></td><td>Whether the user's email address be verified when created. The default value is <code>false</code>.</td></tr><tr><td><code>customFields</code></td><td><code>{ twitter: '@example' }</code></td><td>Any custom fields the user should have on their account. The default value is <code>undefined</code>.</td></tr></tbody></table>

{% hint style="info" %}
To save `customFields` you must first define the `customFields` in the admin panel (**Administration** > **Settings** > **Accounts** > **Registration** > **Custom FIelds**).
{% endhint %}

## Example Call

{% code overflow="wrap" %}
```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.create \
     -d '{
          "name": "name", 
          "email": "email@user.tld", 
          "password": "anypassyouwant", 
          "username": "uniqueusername", 
          "roles":["bot","user"]}'
```
{% endcode %}

## Example Response

```javascript
{
   "user": {
      "_id": "BsNr28znDkG8aeo7W",
      "createdAt": "2016-09-13T14:57:56.037Z",
      "services": {
         "password": {
            "bcrypt": "$2a$i7BFS55uFYRf5TE4ErSUH8HymMNAbpMAvsOcl2C"
         }
      },
      "username": "uniqueusername",
      "emails": [
         {
            "address": "email@user.tld",
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
      "name": "name",
      "settings": {}
   },
   "success": true
}
```

## Change Log

<table><thead><tr><th width="321">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.48.0</td><td><code>role</code> property is now <code>roles</code> which is an array of strings for the roles to create the user with.</td></tr><tr><td>0.45.0</td><td>Users created via this now join the default channels.</td></tr><tr><td>0.40.0</td><td>Added</td></tr></tbody></table>
