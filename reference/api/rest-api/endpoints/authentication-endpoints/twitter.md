# Login with Twitter

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/login</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="245.33333333333331">Key</th><th width="178">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>serviceName</code><mark style="color:red;"><code>*</code></mark></td><td><code>twitter</code></td><td>The desired OAuth service name. In this case, <code>twitter</code>.</td></tr><tr><td><code>accessToken</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>Access token provided by Twitter OAuth.</td></tr><tr><td><code>accessTokenSecret</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>The access token secret provided by Twitter OAuth.</td></tr><tr><td><code>appSecret</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>The app secret provided by Twitter.</td></tr><tr><td><code>appId</code><mark style="color:red;"><code>*</code></mark></td><td><code>hash</code></td><td>The app ID provided by Twitter.</td></tr><tr><td><code>expiresIn</code><mark style="color:red;"><code>*</code></mark></td><td><code>200</code></td><td>Lifetime of token (in seconds).</td></tr></tbody></table>

## Example Call - As JSON

{% code overflow="wrap" %}
```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ 
            "serviceName": "twitter", 
            "accessToken": "hash", 
            "accessTokenSecret": "hash",
            "appSecret": "hash", 
            "appId": "hash", 
            "expiresIn": 200}'
```
{% endcode %}

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
