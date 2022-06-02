# OAuth2 Client

The Rocket.Chat App OAuth2 workflow is a feature that lets developers handle OAuth2 authentication on their apps directly within Rocket.Chat

### OAuth2 Setup

* Start by importing the methods needed from the IOAuth2 definition in the main class of your app.

```
import { IAuthData } from '@rocket.chat/apps-engine/definition/oauth2/IOAuth2';
import { createOAuth2Client } from '@rocket.chat/apps-engine/definition/oauth2/OAuth2';
```

* In setting up the configurations of the app using the extendConfiguration method, we create an instance of the createOAuth2Client we imported above.

```
protected async extendConfiguration(configuration: IConfigurationExtend): Promise<void> {
        try {
            await createOAuth2Client(this, this.config)
                .setup(configuration);
            await configuration.slashCommands.provideSlashCommand(new AuthCommandCommand(this));
        } catch (error) {
            this.getLogger().error('[extendConfiguration] error', error);
        }
    }
```

* The `createOAuth2Client` method takes in two parameters, `createOAuth2Client(this, this.config)` being the app itself and an object with props as configuration.\
  Below is a sample of the config parameter as seen in the [definition documentation](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/oauth2\_ioauth2.ioauth2clientoptions.html)

```
private config = {
        alias: 'test',
        accessTokenUri: 'https://oauth2.googleapis.com/token',
        authUri: 'https://accounts.google.com/o/oauth2/v2/auth',
        refreshTokenUri: 'https://oauth2.googleapis.com/token',
        revokeTokenUri: 'https://oauth2.googleapis.com/revoke',
        callback: this.autorizationCallback.bind(this),
    };
```

* Now calling the `setup(configuration)` method on the `createOAuth2Client` creates all the setup APIs you need to use.

### Using OAuth2

After setup, however, you want to go about implementing OAuth2 on your app is dependent on you.

The OAuth2Client gives you access to [multiple methods](oauth2-client.md#oauth2-setup) like _getAccessTokenForUser_, _getAccessTokenForUser_, _revokeUserAccessToken_ etc.
