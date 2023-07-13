# Login

Log in a user.&#x20;

Rocket.Chat supports various methods of authentication. The list of supported auth services (and their configurations) are in the `meteor_accounts_loginServiceConfiguration` collection.

## Using username and password

To ensure the security of the user's account, it is important not to submit the user's password as plain text. Instead, apply a hashing algorithm (_**for example - sha-256**_).&#x20;

{% hint style="info" %}
The digest must be lowercase.
{% endhint %}

### Payload Parameters

| Argument   | Example                                                                                                                                                                   | Required | Description                                                                |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------- |
| `user`     | <pre><code>{ "username": "him" }
</code></pre>                                                                                                                            | Required | The user object containing either the username or email.                   |
| `password` | <pre><code>{
                "digest": "52c53f4abbfe42e1ccd4fd9d864453ee57f8efbd4c9ecec6d88bd83d7f7a9c02",
                "algorithm":"sha-256"
         }
</code></pre> | Required | The password object containing the hashed password and the hash algorithm. |

### Example Call

```
{
    "msg": "method",
    "method": "login",
    "id":"42",
    "params":[
        {
            "user": { "username": "him" },
            "password": {
                "digest": "52c53f4abbfe42e1ccd4fd9d864453ee57f8efbd4c9ecec6d88bd83d7f7a9c02",
                "algorithm":"sha-256"
            }
        }
    ]
}
```

### Example Response

#### Success

```
{
    "msg": "result",
    "id": "42",
    "result": {
        "id": "3Dw26TXWxvi8gwfgM",
        "token": "72kB2z5SpnWG-vOSKaAXku74PV851pVOVAoC67FpFEI",
        "tokenExpires": {
            "$date": 1696417505309
        },
        "type": "password"
    }
}
```

#### Error

```
{
    "msg": "result",
    "id": "42",
    "error": {
        "error": 403,
        "reason": "Incorrect password",
        "message": "Incorrect password [403]",
        "errorType": "Meteor.Error"
    }
}
```

## Using an authentication token

You can use a previous user authentication token or a [Personal Access Token](https://docs.rocket.chat/guides/user-guides/user-panel/managing-your-account/personal-access-token) to log in a user.

### Payload Parameters

| Argument | Example                                      | Required | Description                                                |
| -------- | -------------------------------------------- | -------- | ---------------------------------------------------------- |
| `resume` | `5BwhTeEXiTmU_8uKxGuy4pqWRHRP73QpJYmoSWfBpc` | Required | A personal access token or previous authToken of the user. |

### Example Call

<pre><code>{
    "msg": "method",
    "method": "login",
    "id": "42",
<strong>    "params":[
</strong>        { "resume": "auth-token" }
    ]
}
</code></pre>

### Example Response

{% hint style="info" %}
This success response format remains the same irrespective of the login method used.&#x20;
{% endhint %}

```
{
    "msg": "result",
    "id": "42",
    "result": {
        "id": "LFdhbcNHx5zsMA7T4",
        "token": "5BwhTeEXiTmU_8uKxGuy4pqWRHRP73QpJYmoSWfBpcB",
        "tokenExpires": {
            "$date": 1696418806422
        },
        "type": "resume"
    }
}
```

{% hint style="info" %}
If the `auth-token` is expired, send another[ login request](../../../rest-api/endpoints/authentication-endpoints/login.md) to get a new `authToken` with a new expiration date.
{% endhint %}

## Using Authentication providers

&#x20;OAuth is used to support additional auth providers.

### Example Call

```javascript
{
    "msg": "method",
    "method": "login",
    "id":"42",
    "params": [
        {
            "oauth": {
                "credentialToken":"credential-token",
                "credentialSecret":"credential-secret"
            }
        }
    ]
}
```
