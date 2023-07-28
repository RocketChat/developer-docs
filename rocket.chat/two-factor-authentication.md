# Two Factor Authentication

Rocket.Chat's Two-Factor Authentication (2FA) is a robust security feature that significantly enhances the protection of user accounts. It operates on the principle of "something you know and something you have," requiring not only a password and username but also a unique piece of information only the user possesses on them, i.e., a second factor.

**Sources for Two-Factor Code**: Users have a variety of sources for generating the two-factor code:

1. **Authenticator App**: Users can configure apps like Google Authenticator or Authy to generate the 2FA code.
2. **Email**: Users with verified emails cann receive the 2FA code via email.
3. **Password**:Although not a two-factor method in itself, the password serves as a fallback for cases where the user has no other 2FA option configured. However, this password fallback is disabled for the login process to prevent the system from requiring the password twice when the user has no other 2FA method configured.

**API Calls and Two-Factor Authentication**: Any DDP Method or REST call may require two-factor authentication. Therefore, it's recommended to create a wrapper for your calls to handle the errors and execute the request again, passing the required info.

**Trusted Clients**: By default, after a two-factor validation, the client used (a hash of user-agent + IP address) will be trusted for 5 minutes. This duration is configurable in the workspace administration. Some methods may disable this feature, forcing the API to always require the two-factor for that method/endpoint. The method to disable the two-factor by email and the login are examples. We are using the error `totp-required` for compatibility purposes, it doesn't mean that the error is related to TOTP only, so we pass more details to identify the action required.

**Personal Access Tokens**: **Personal Access Tokens**: Personal Access Tokens are a unique feature of Rocket.Chat's 2FA system. Users can create these tokens, which do not expire and can bypass the 2FA requirement. This feature is particularly useful for users who need to maintain long-term integrations or automated processes with their Rocket.Chat account. However, it's crucial to keep these tokens secure and confidential, as a compromised token could provide unrestricted access to the user's account.

**Realtime API and REST API**: For more detailed information on how Two-Factor Authentication works with the [Realtime API](../reference/api/realtime-api/method-calls/authentication/realtime-two-factor-authentication.md) and [REST API](../reference/api/rest-api/endpoints/authentication-endpoints/rest-two-factor-authentication.md), you can visit the respective pages on the Rocket.Chat developer documentation.

In summary, Rocket.Chat's Two-Factor Authentication feature, combined with the use of Personal Access Tokens, provides a balance of security and convenience. It provides robust protection for user accounts while facilitating seamless integrations and interactions with other applications and services.
