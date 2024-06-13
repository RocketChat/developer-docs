# Login with Username and Password

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/login</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="195.33333333333331">Key</th><th width="261">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>user</code></td><td><code>foo@bar.com</code> OR <code>myusername</code></td><td>Your username or email.</td></tr><tr><td><code>password</code></td><td><code>my$up3erP@ssw0rd</code></td><td>Your password.</td></tr><tr><td><code>resume</code></td><td><code>9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq</code></td><td>Your previously issued <code>authToken</code>.</td></tr></tbody></table>

{% hint style="info" %}
* Whilst none of the arguments are required in every request, every request requires some arguments to be provided. You MUST provide either `user` AND `password`, or provide `resume`.
* You will need to provide the `authToken` and `userId` for any of the authenticated methods.
* If your user has two-factor(2FA) authentication enabled, you must send a request like [this](rest-two-factor-authentication.md).
* If LDAP authentication is enabled, you must maintain the login in the same way as you normally do. Similarly, if 2FA is enabled for an LDAP user, everything stays the same.
{% endhint %}

## Example Call - As Form Data

With username and password:

```bash
curl http://localhost:3000/api/v1/login \
     -d "user=myusername&password=mypassword"
```

With email and password:

```bash
curl http://localhost:3000/api/v1/login \
     -d "user=my@email.com&password=mypassword"
```

## Example Call - As JSON

With username and password:

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ "user": "myusername", "password": "mypassword" }'
```

With email and password:

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ "user": "my@email.com", "password": "mypassword" }'
```

## Example Call - When two-factor(2FA) authentication is enabled

With user, password, and code:

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ "user": "myusername", "password": "mypassword", "code": "224610" }'
```

With email, password, and code:

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ "user": "my@email.com", "password": "mypassword", "code": "224610" }'
```

## Example Response

```json
{
  "status": "success",
  "data": {
      "authToken": "9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq",
      "userId": "aobEdbYhXfu5hkeqG",
      "me": {
            "_id": "aYjNnig8BEAWeQzMh",
            "name": "Rocket Cat",
            "emails": [
                {
                  "address": "rocket.cat@rocket.chat",
                  "verified": false
                }
            ],
            "status": "offline",
            "statusConnection": "offline",
            "username": "rocket.cat",
            "utcOffset": -3,
            "active": true,
            "roles": [
                "admin"
            ],
            "settings": {
                "preferences": {}
              },
            "avatarUrl": "http://localhost:3000/avatar/test"
        }
   }
}
```

## Change Log

| Version | Description                            |
| ------- | -------------------------------------- |
| 1.0.0   | Added `avatarUrl` property to response |
| 0.64.0  | Added `me` property to response        |
| 0.60.0  | Added                                  |
