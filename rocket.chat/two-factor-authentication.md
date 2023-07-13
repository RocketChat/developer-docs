# Two Factor Authentication

Rocket.Chat uses Two Factor to authorize important actions. There is a list of possible sources for the two-factor code:

* **Authenticator App**: like Google Authenticator or Authy (need to be configured by the user);
* **Email**: users will receive the code via email (configured by default and enabled for those users with verified emails);
* **Password\***: it's not a two factor by itself, but a fallback for the cases where the user has no other option to configure;

> \* The password fallback is disabled for the login process, so the login will not require the password twice when the user has no other two factor method configure.

Any **DDP Method** or **REST call** may have the two-factor requirement; for that reason, we suggest creating a wrapper for your calls to handle the errors described here and executing the request again, passing the required info as we will describe here as well.

## Remember Me

By default, after a two-factor validation, the client used (a hash of user-agent + IP address) will be trusted for 5 minutes. It's configurable via the admin panel.

Some methods may disable this feature forcing the API to always require the two-factor for that method/endpoint. The method to disable the two-factor by email and the login are examples.

## Compatibility

We are using the error `totp-required` for compatibility purposes, it doesn't mean that the error is related to TOTP only, so we pass more details to identify the action required.

## Personal Access Tokens

Personal Access Tokens are tokens created by the users (when enabled by the server) and commonly used to give access to other applications, bots, etc. Those tokens do not expire, and they have the option to **bypass** the Two-Factor (required by default), allowing users to use their integrations without restrictions when needed.

Now it's the two-factor required to create personal access tokens.

> The bypass should be used carefully because it gives super powers to who gain access to the token

## Realtime API

Visit the [Two Factor Authentication](../reference/api/realtime-api/method-calls/authentication/2fa.md) page at Realtime API guides for more information.

## REST API

Visit the [Two Factor Authentication](../reference/api/rest-api/endpoints/authentication-endpoints/2fa.md) page at REST API guides for more information.
