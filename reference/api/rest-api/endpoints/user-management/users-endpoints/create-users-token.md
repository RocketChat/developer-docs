# Create Users Token

Create a user authentication token. This is the same type of session token a user would get via login and will expire the same way.

{% hint style="info" %}
* To be able to use this endpoint, you must set the [Environment variable](https://docs.rocket.chat/deploy/rocket.chat-environment-configuration/environment-variables) `CREATE_TOKENS_FOR_USERS=true`.
* For SaaS workspaces, [contact support](https://docs.rocket.chat/resources/get-support) to set this variable.
{% endhint %}

{% hint style="info" %}
You are required to have the `user-generate-access-token` permission.
{% endhint %}

For example, if you use Snaps to deploy, set the environment variable as shown below:

{% code overflow="wrap" %}
```
echo "CREATE_TOKENS_FOR_USERS=true" > /var/snap/rocketchat-server/common/create-tokens.env
sudo systemctl restart snap.rocketchat-server.rocketchat-server.service
```
{% endcode %}

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.createToken</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="194.33333333333331">Key</th><th width="226">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code> or <code>test</code></td><td>The ID or username of the user.</td></tr></tbody></table>

## Example Call

With `userId`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.createToken \
     -d '{ 
          "userId": "BsNr28znDkG8aeo7W" }'
```

With `username`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.createToken \
     -d '{ "username": "test" }'
```

## Example Response

```json
{
  "data": {
    "userId": "BsNr28znDkG8aeo7W",
    "authToken": "2jdk99wuSjXPO201XlAks9sjDjAhSJmskAKW301mSuj9Sk",
  },
  "success": true
}
```

## Change Log

<table><thead><tr><th width="330">Version</th><th>Description</th></tr></thead><tbody><tr><td>2.1.0</td><td>Added ENV VAR to be able to use this endpoint (process.env.CREATE_TOKENS_FOR_USERS).</td></tr><tr><td>0.56.0</td><td>Added</td></tr></tbody></table>
