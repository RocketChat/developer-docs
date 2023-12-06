# Login with Facebook

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/login</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="230.33333333333331">Key</th><th width="178">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>serviceName</code><mark style="color:red;"><code>*</code></mark></td><td><code>facebook</code></td><td>The desired OAuth service name. In this case, <code>facebook</code>.</td></tr><tr><td><code>accessToken</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>Access token provided by Facebook oauth.</td></tr><tr><td><code>secret</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>The secret provided by Facebook.</td></tr><tr><td><code>expiresIn</code><mark style="color:red;"><code>*</code></mark></td><td><code>200</code></td><td>Lifetime of token (in seconds).</td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ 
            "serviceName": "facebook", 
            "accessToken": "hash",
            "secret": "hash", 
            "expiresIn": 200 }'
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
| 0.63.0  | Added                                  |
