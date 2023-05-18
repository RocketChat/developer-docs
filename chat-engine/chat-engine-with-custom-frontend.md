# Chat Engine with Custom Frontend

The ability to incorporate Rocket.Chat's chat functionalities in your application with a custom frontend allow you to provide a seamless chat experience while maintaining your desired user experience.

The Chat Engine leverages the use of WebSockets API to enable real-time chat functionality.

## Procedure

Following are some important factors to consider when implementing Chat Engine capabilities using a custom frontend.

{% hint style="info" %}
Make sure you do all API calls to Rocket.Chat on the backend to avoid exposing sensitive data.
{% endhint %}

### Authentication and Token Generation

In this scenario, you have your application's login mechanism for end users. However, you need to authenticate the user with Rocket.Chat to provide chat functionality.

To achieve this:

Use a specified Rocket.Chat admin credentials to call the Create User Token API endpoint from your backend for an existing user. This allows your backend service (accessible only to authenticated users on your platform) to request  `Authorization token` from Rocket.Chat for the user. Use this token for subsequent requests to Rocket.Chat.

#### Login Workflow

A typical workflow for logging in a user involves the following steps:

* Once a user is authenticated on your platform, your backend service requests a token session from Rocket.Chat for that user. _(If you don't have a corresponding user on Rocket.Chat yet, you can create it using the Create User API endpoint)_.
* The backend receives the `userId` and `authToken` from the Create Token API response.
* These credentials (`userId` and `authToken` are then used for all subsequent Rocket.Chat API calls and embeddings that require authorization.

{% hint style="info" %}
The `authToken` has an expiry time set. Be sure to refresh when it expires.
{% endhint %}

#### Logout Mechanism

When a user navigates to another page, they must be reauthenticated. You can simulate the logout process appropriately by calling the Logout API endpoint. This causes the `authToken` to expire.

### User Interface

You can structure the user interface as much as you can by utilizing the endpoints available.

A typical example is:\
Upon successful login, the application presents the user with a list of Rooms to which the user has access. When the user selects a room, an iframe is populated with the corresponding embedded URL for that channel or room.

Read more about the iframe embed in [chat-engine-in-iframe.md](chat-engine-in-iframe.md "mention").
