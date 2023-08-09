# Configuring iFrame auth

Iframe authentication in Rocket.Chat enables user authentication via your custom login page in your web application, rather than the Rocket.Chat login page. This can be useful if you want to have a single sign-on system for your website and Rocket.Chat. This guide will walk you through setting up iFrame authentication in Rocket.Chat.&#x20;

To enable iframe integration in your workspace,&#x20;

* Navigate to **Administration > Workspace > Settings > Accounts > Iframe** and toggle on **enabled**.

When enabled, Rocket.Chat communicates with a third-party application to verify if a user is logged in. If the user isn't authenticated, Rocket.Chat displays the iFrame URL within an iFrame, enabling them to log in on the third-party website. This process ensures the user's authentication not just on the third-party site but also within Rocket.Chat.

You can use your own login page or API to log people into Rocket.Chat using iframe auth. If Rocket.Chat is enabled on your workspace, it sends a `XMLHttpRequest` to the iFrame API URL to see if the user is logged in at the third-party application. If it doesn't succeed, then Rocket.Chat presents the iframe URL within an iframe for the user to log in on the third-party website, therefore authenticating the user on Rocket.Chat as well.

{% hint style="info" %}
For more information on the iframe authentication flow, see this [NodeJs example app](https://github.com/RocketChat/iframe-auth-example).
{% endhint %}

**Configuring API URL and API Method**

Rocket.Chat utilizes an API URL and API Method to facilitate user login and authentication verification within your third-party application. The **API URL** is an endpoint on your third-party application that is responsible for confirming the user's login status. The **API Method** is used to select the submission method Rocket.Chat will use to submit information to the **API URL,** e.g., `POST`. When a user is logged into the third-party application, the API URL connects with Rocket.Chat and sends back a JSON object containing a `token` or `loginToken` property. If the user is not logged in, the **API URL** responds with an empty body and a 401 status code. The property returned by the API URL varies based on how the third-party application interacts with Rocket.Chat.&#x20;

**Interacting with Rocket.Chat Iframe**

Interaction with Rocket.Chat iframe can be through the [**using Rocket.Chat API**](./#using-rocket.chat-api) or [**Managing MongoDB directly**](./#managing-mongodb-directly).

* **Using Rocket.Chat API**: You can use[ Rocket.Chat's REST APIs ](https://developer.rocket.chat/reference/api/rest-api/endpoints/other-important-endpoints/authentication-endpoints/login)to authenticate the user if you have the user's password stored or if it is the same between your third-party system and Rocket.Chat. This way, you receive an `authToken` back from Rocket.Chat that should be returned as `loginToken` by your endpoint. If the user does not have a Rocket.Chat account, you can either  [create a user](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/create-user-endpoint) as an admin orr [register them](https://developer.rocket.chat/reference/api/rest-api/endpoints/team-collaboration-endpoints/users-endpoints/register-user) using the Rocket.Chat REST API..yet;;

```javascript
{
  "loginToken": "already-saved-or-returned-login-token"
}
```

* **Managing MongoDB directly**: Here, you have access to Rocket.Chat's database, you can connect there directly and manage the user records yourself. It is useful if you already have MongoDB on your stack and don't want to learn Rocket.Chat's API. The endpoint should connect to Rocket.Chat's MongoDB database and ensure the `generated-token` is saved on `users` collection on the corresponding user record. The `generated-token` should be saved on the field path `services.iframe.token`. Here is a snippet of the user record:

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

**IFrame URL**

IFrame URL is the URL of the webpage you want to embed as the login page of your Rocket.Chat instance. It can be developed using any programming language/framework of your choice. This login page communicates back to Rocket.Chat using `postMessage` API. When a user logs in to your website or application, you need to authenticate them with Rocket.Chat so that they can access the chat functionality. This authentication process involves sending a request to Rocket.Chat's API URL endpoint with the user's login credentials. Once the user is authenticated, render the chat interface within an iframe on your application. To do this, return a JavaScript code to execute within the iframe and handle the authentication on the Rocket.Chat side. This Javascript code varies depending on how you logged in the user.&#x20;

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

**Using OAuth configured on Rocket.Chat's auth**

Suppose you have OAuth services configured on Rocket.Chat, you can trigger them from within your login page as well. To implement this authentication, you will receive a `postMessage` back from Rocket.Chat after triggering the OAuth authentication with the user's credentials response from the OAuth service. You need to manage the user creation/authentication on Rocket.Chat's database by yourself, as described earlier.

1. **Facebook**

```javascript
window.parent.postMessage({
  event: 'call-facebook-login',
  permissions: ['email']
}, 'http://your.rocket.chat.url');
```

The reply will be either a postMessage or an error back to your page.

**PostMessage**

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

**Error**

```javascript
{
  event: 'facebook-login-error',
  error: error,
  response: response
}
```

2**. Google**

```javascript
window.parent.postMessage({
  event: 'call-google-login',
  //  scopes:
  //  webClientId:
}, 'http://your.rocket.chat.url');
```

The reply will be either a postMessage or an error back to your page.

**PostMessage**

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

**Error**

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

The reply will be either a postMessage or an error back to your page.

**PostMessage**

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

**Error**

```javascript
{
  event: 'twitter-login-error',
  error: error
}
```

**Login in Rocket.Chat with the default account system while in development**

When you activate the iframe auth, you cannot access Rocket.Chat's default login page, however, if you still want to use your Rocket.Chat's credentials to log in, you can do that by opening the browser's developer console and executing the following code:

```javascript
Meteor.loginWithPassword('username-or-email', 'your-password');
```

With the iframe authentication properly set up, let's now move forward to [testing-the-iframe-authentication.md](../../../rocket.chat/iframe-integration/configuring-iframe-auth/testing-the-iframe-authentication.md "mention").
