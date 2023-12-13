# Delete User

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `delete-user`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="231">Key</th><th width="221">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code> or <code>test</code></td><td>The ID or username of the user.</td></tr><tr><td><code>confirmRelinquish</code></td><td><code>true</code></td><td>Deletes user even if it is the last owner of a room. The default value is <code>false</code>.</td></tr></tbody></table>

## Example Call

With `userID`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.delete \
     -d '{ 
          "userId": "BsNr28znDkG8aeo7W" }'
```

With `username`:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.delete \
     -d '{ 
          "username": "test" }'
```

## Example Response

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description                               |
| ------- | ----------------------------------------- |
| 3.7.0   | Added `confirmRelinquish` to the payload. |
| 0.35.0  | Added                                     |
