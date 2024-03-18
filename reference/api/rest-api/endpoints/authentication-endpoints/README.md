# Authentication

Rocket.Chat provides diverse authentication methods for secure API communication, spanning from basic [username and password authentication](login.md) to OAuth integration with services such as [Google](google.md), [Facebook](facebook.md), and [Twitter](twitter.md).

To access protected endpoints in the Rocket.Chat API, you must include the userId and a valid authentication token of the user as headers in the request. Add the authentication token as `x-Auth-Token` and the userId as `x-User-Id`  in the headers of your request.

#### Authentication Tokens

Authentication tokens are unique identifiers confirming a user's active session within your Rocket.Chat workspace. These tokens validate the user's identity and permissions, providing secure access to various features and resources. When making requests to protected endpoints that mandate authentication, add this authentication token as `x-Auth-Token` header in your request.

In Rocket.Chat, there are primarily two types of authentication tokens: **authToken** and **personal access token**.

1.  **authToken**

    `authToken` is a temporary authentication token returned to users after a successful login through any login endpoint. Additionally, workspace administrators can create `authtoken` for a user via the [Create User Token](../user-management/users-endpoints/create-users-token.md) endpoint.
2.  **personal access token**

    [Personal Access Tokens](https://docs.rocket.chat/use-rocket.chat/user-guides/user-panel/account#personal-access-tokens) are permanent authentication tokens that users can generate for themselves to access the API securely without exposing their primary credentials. Visit the [Generate Personal Access Tokens API guide](../user-management/users-endpoints/generatepersonalaccesstoken.md) for more details.
