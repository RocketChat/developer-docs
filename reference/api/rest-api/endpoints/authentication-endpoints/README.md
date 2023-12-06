# Authentication

To access the Rocket.Chat API, you need to log in using your `username` and `password`. This authentication method allows you to interact securely with the Rocket.Chat server and perform actions on behalf of the authenticated user.

Upon successful authentication, the API will provide an authentication token (`authToken`) and a unique user identifier (`userId`) as part of the JSON response. These values should be used as headers in subsequent requests to protected endpoints that require authentication.

{% hint style="info" %}
The `authToken`is passed as `X-Auth-Token` header, while the `userId` as `X-User-Id` header.
{% endhint %}

The Rocket.Chat API also supports other forms of authentication using OAuth apps like [Facebook](facebook.md), [Google](google.md), and [Twitter](twitter.md). Go to the subsequent endpoint topics to know more.
