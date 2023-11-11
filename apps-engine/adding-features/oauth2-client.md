# OAuth2 Client

The Rocket.Chat App OAuth2 workflow is a feature that lets developers handle OAuth2 authentication on their apps directly within Rocket.Chat

### OAuth2 Setup

1. Import the methods needed from the [`IOAuth2`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/modules/oauth2\_ioauth2.html) and [`OAuth2`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/modules/oauth2\_oauth2.html) definitions in the main class of your app.

```
import { IAuthData } from '@rocket.chat/apps-engine/definition/oauth2/IOAuth2';
import { createOAuth2Client } from '@rocket.chat/apps-engine/definition/oauth2/OAuth2';
```

2. When setting up the app configurations using the `extendConfiguration` method, we create an instance of the `createOAuth2Client` imported above.

{% code lineNumbers="true" %}
```typescript
protected async extendConfiguration(configuration: IConfigurationExtend): Promise<void> {
    const oauthConfig = {
            alias: 'test',
            accessTokenUri: 'https://oauth2.googleapis.com/token',
            authUri: 'https://accounts.google.com/o/oauth2/v2/auth',
            refreshTokenUri: 'https://oauth2.googleapis.com/token',
            revokeTokenUri: 'https://oauth2.googleapis.com/revoke',
    };

    try {
        await createOAuth2Client(this, oauthConfig)
            .setup(configuration);
    } catch (error) {
        this.getLogger().error('[extendConfiguration] error', error);
    }
}
```
{% endcode %}

* The `createOAuth2Client` method takes in two parameters:
  * `app`: The app itself.
  * `options`: An object with props as configuration - see the [definition documentation](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/oauth2\_ioauth2.ioauth2clientoptions.html) for more details.
* Now calling the `setup(configuration)` method on the `createOAuth2Client` creates all the setup APIs you need to use.

### Use OAuth2

After setup, use the `OAuth2Client` to access [multiple methods](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/oauth2\_ioauth2.ioauth2client.html) like _`getAccessTokenForUser`_, _`revokeUserAccessToken`_ etc.

#### `getAccessTokenForUser`

Gets the token information for a specific user, if available. This receives the user instance as a parameter and returns data about the authenticated user.

```typescript
await createOAuth2Client(this, this.config).getAccessTokenForUser(user);
```

#### `getUserAuthorizationUrl`

Returns the authorization URL to which the user must be redirected in order to authorize access to the application.

```typescript
const url = await createOAuth2Client(this, this.config).getUserAuthorizationUrl(user);
```

#### `refreshUserAccessToken`

Refreshes the user's access token. This is useful when the user access token has expired.

```typescript
await createOAuth2Client(this, this.config).refreshUserAccessToken(user, persis);
```

#### `revokeUserAccessToken`

Revokes user's access token in the service provider. When successfully executed, users will need to be authenticated again before using the service.

```typescript
await createOAuth2Client(this, this.config).revokeUserAccessToken(user, persis);
```
