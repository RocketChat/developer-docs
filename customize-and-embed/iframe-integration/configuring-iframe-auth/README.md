# Configuring iframe auth

If you want to authenticate users using your own login page in place of the Rocket.Chat's login page via the iframe integration, go to **Administration > Workspace > Settings > Accounts > Iframe** and enable it:

* [How to use iframe integration for authentication](./)

With `iframe` auth, you can use your own authentication page/API to log in users on Rocket.Chat.

Using iframe auth, you can use your authentication page to log in users on your Rocket.Chat workspace.  If enabled, Rocket.Chat sends a `XMLHttpRequest` to the iFrame API URL to see if the user is logged in at the third-party website. If it doesn't succeed, then Rocket.Chat presents the iframe URL within an iframe. for the user to log in on the third-party website, therefore authenticating the user on Rocket.Chat as well.

{% hint style="info" %}
See our [NodeJs example app](https://github.com/RocketChat/iframe-auth-example) on iframe auth to understand the authentication flow.
{% endhint %}

## Configuring API URL and API Method

Rocket.Chat uses **API URL** and **API Method** to log in users or verify their authentication status in a third-party application.&#x20;

**API URL** is an endpoint on the third-party application that checks if the user is already logged in to that system.&#x20;

The **API Method** is used to select the submission method Rocket.Chat will use to submit information to the **API URL,** e.g., `POST`.

If the user has already logged into the third-party system, the **API URL** communicates to Rocket.Chat and returns a JSON object containing either a `token` or `loginToken` property. If the user is not already logged in, the **API URL** returns an empty body with the status `401`.

The property returned by the **API URL** depends on how the third-party system interfaces with Rocket.Chat. This interface can be through the [**using Rocket.Chat API**](./#using-rocket.chat-api) or [**Managing MongoDB directly**](./#managing-mongodb-directly).

### Using Rocket.Chat API&#x20;

You can use[ Rocket.Chat's REST APIs ](https://developer.rocket.chat/reference/api/rest-api/endpoints/other-important-endpoints/authentication-endpoints/login)to authenticate the user if you have the user's password stored or if it is the same between your third-party system and Rocket.Chat. This way, you receive an `authToken` back from Rocket.Chat that should be returned as `loginToken` by your endpoint.

At this point, if the user does not have a Rocket.Chat account yet; you can either use Rocket.Chat API to [create a user](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-user-endpoint) using an admin account or [register them](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/register-user).

After you log the user in, you should return a payload like the following:

```javascript
{
  "loginToken": "already-saved-or-returned-login-token"
}
```

### Managing MongoDB directly

Here, you have access to Rocket.Chat's database, you can connect there directly and manage the user records yourself. It is useful if you already have MongoDB on your stack and don't want to learn Rocket.Chat's API.

The endpoint should connect to Rocket.Chat's MongoDB database and ensure the `generated-token` is saved on `users` collection on the corresponding user record. The `generated-token` should be saved on the field path `services.iframe.token`. Here is a snippet of the user record:

```javascript
{
  "_id": "MZiFvWAf96876875u",
  "createdAt": new Date(1432252673528),
  "services": {
    "iframe": {
      "token": "generated-token"
    }
  },
  "emails": [
    {
      "address": "useremail@gmail.com",
      "verified": true
    }
  ],
  "name": "John Doe",
  "username": "john.doe",
  "active": true,
  "statusDefault": "online",
  "roles": [
    "user"
  ],
  "type": "user"
}
```

Here is a snippet of the response:

```javascript
{
  "token": "generated-token"
}
```

## IFrame URL

IFrame URL is the URL of the webpage you want to embed as the login page of your Rocket.Chat instance. It can be developed using any programming language/framework of your choice. This login page communicates back to Rocket.Chat using `postMessage` API.

When a user logs in to your website or application, you need to authenticate them with Rocket.Chat so that they can access the chat functionality. This authentication process involves sending a request to Rocket.Chat's API URL endpoint with the user's login credentials.&#x20;

Once the user is authenticated, render the chat interface within an iframe on your application. To do this,  return a JavaScript code to execute within the iframe and handle the authentication on the Rocket.Chat side.&#x20;

This code Javascript depends on how you logged in the user:

* If you have used Rocket.Chat's APIs to log in the user or already have user's token saved in your end, return:

```javascript
<script>
window.parent.postMessage({
  event: 'login-with-token',
  loginToken: 'your-token'
}, 'http://your.rocket.chat.url');
</script>
```

* If you have saved user's token connecting directly to Rocket.Chat's database on the user's field `services.iframe.token`:

```javascript
<script>
window.parent.postMessage({
  event: 'try-iframe-login'
}, 'http://your.rocket.chat.url');
</script>
```

### Using OAuth configured on Rocket.Chat's end

Suppose you have OAuth services configured on Rocket.Chat, you can trigger them from within your login page as well.

To implement this authentication, you will receive a postMessage back from Rocket.Chat after triggering the OAuth authentication with the user's credentials response from the OAuth service. You need to manage the user creation/authentication on Rocket.Chat's database by yourself, as described earlier.

#### Facebook

```javascript
window.parent.postMessage({
  event: 'call-facebook-login',
  permissions: ['email']
}, 'http://your.rocket.chat.url');
```

The reply will be a postMessage back to your page with:

```javascript
{
  event: 'facebook-login-success',
  response: {
    // authResponse: Object
    // accessToken: "a7s6d8a76s8d7..."
    // expiresIn: "5172793"
    // secret: "..."
    // session_key: true
    // sig: "..."
    // userID: "675676576"
    // status: "connected"
  }
}
```

Or an error

```javascript
{
  event: 'facebook-login-error',
  error: error,
  response: response
}
```

#### Google

```javascript
window.parent.postMessage({
  event: 'call-google-login',
  //  scopes:
  //  webClientId:
}, 'http://your.rocket.chat.url');
```

The reply will be a postMessage back to your page with:

```javascript
{
  event: 'google-login-success',
  response: {
    // "email": "rodrigoknascimento@gmail.com",
    // "userId": "1082039180239",
    // "displayName": "Rodrigo Nascimento",
    // "gender": "male",
    // "imageUrl": "https://lh5.googleusercontent.com/-shUpniJA480/AAAAAAAAAAI/AAAAAAAAAqY/_B8oyS8yBw0/photo.jpg?sz=50",
    // "givenName": "Rodrigo",
    // "familyName": "Nascimento",
    // "ageRangeMin": 21,
    // "oauthToken": "123198273kajhsdh1892h"
  }
}
```

Or an error

```javascript
{
  event: 'google-login-error',
  error: error
}
```

#### Twitter

```javascript
window.parent.postMessage({
  event: 'call-twitter-login'
}, 'http://your.rocket.chat.url');
```

The reply will be a postMessage back to your page with:

```javascript
{
  event: 'twitter-login-success',
  response: {
    // "userName": "orodrigok",
    // "userId": 293123,
    // "secret": "asdua09sud",
    // "token": "2jh3k1j2h3"
  }
}
```

Or an error

```javascript
{
  event: 'twitter-login-error',
  error: error
}
```

## How to login in Rocket.Chat with the default account system while in development.

When you activate the iframe auth, you cannot access Rocket.Chat's default login page, however, if you still need/want to use your Rocket.Chat's credentials to log in, you can do that by opening the browser's developer Console and executing the following code:

```javascript
Meteor.loginWithPassword('username-or-email', 'your-password');
```
