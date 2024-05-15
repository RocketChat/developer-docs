# Register API Endpoints

In this example, we will register a public API endpoint that receives data from external HTTP requests. We will forward the data received from the endpoint to the `#general` channel.

## Register an API endpoint

First of all, let's create a new Rocket.Chat app from scratch using `rc-apps create.` (If `rc-apps` is an unrecognized command, please check out the [Getting Started ](https://developer.rocket.chat/apps-engine/getting-started)section to make initial preparations first).

In the main `App` class, we need to implement the `extendConfiguration` method, within which we use `configuration.api.provideApi` to register a new API endpoint `new Endpoint(this)`.

{% code lineNumbers="true" fullWidth="false" %}
```typescript
// Main App Class
import { IAppAccessors, IConfigurationExtend, ILogger } from '@rocket.chat/apps-engine/definition/accessors';
import { ApiSecurity, ApiVisibility } from '@rocket.chat/apps-engine/definition/api';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';

import { Endpoint } from './endpoint';

export class RocketChatTester extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async extendConfiguration(configuration: IConfigurationExtend) {
        // Register API endpoints
        await configuration.api.provideApi({
            visibility: ApiVisibility.PUBLIC,
            security: ApiSecurity.UNSECURE,
            endpoints: [new Endpoint(this)],
        });
    }
}
```
{% endcode %}

## Create an `endpoint` class

Notice that we imported an `Endpoint` class from another file. Now, let's create a new file named `endpoint.ts` and implement the class `Endpoint` we used above.

{% code lineNumbers="true" fullWidth="false" %}
```typescript
// endpoint.ts
import { HttpStatusCode, IHttp, IModify, IPersistence, IRead } from '@rocket.chat/apps-engine/definition/accessors';
import { ApiEndpoint, IApiEndpointInfo, IApiRequest, IApiResponse } from '@rocket.chat/apps-engine/definition/api';

export class Endpoint extends ApiEndpoint {
    public path = 'api';

    public async post(
        request: IApiRequest, endpoint: IApiEndpointInfo, 
        read: IRead, 
        modify: IModify, 
        http: IHttp, 
        persis: IPersistence,
    ): Promise<IApiResponse> {
        const body = Object.entries(request.content)
            .map(([key, value]) => `${key}: ${value}`)
            .join('\n');
        const room = await read.getRoomReader().getByName('general');

        if (!room) {
            return {
                status: HttpStatusCode.NOT_FOUND,
                content: `Room "#general" could not be found`,
            };
        }

        const messageBuilder = modify.getCreator().startMessage()
            .setText(body)
            .setRoom(room);
        const messageId = await modify.getCreator().finish(messageBuilder);

        return this.success(JSON.stringify({ messageId }));
    }
}
```
{% endcode %}

In the file `endpoint.ts`, we create a class that extends the base class `ApiEndpoint`. We define the path of the API endpoint by assigning the value `'api'` to the public property `path`.

Then, let's implement the method `post`, which will be executed every time the API endpoint receives an `HTTP POST` request from an external service. To forward any data received to the `#general` channel, we obtain the request content by `request.content`, create a message containing the request content, and then send it to the channel `#general`.

## Test the result

[Deploy your app](../getting-started/creating-an-app.md). You can check the complete endpoint URL you registered for the app on the **App Info** page.

![](<../../.gitbook/assets/image (19) (1).png>)

Open the terminal and use curl to post some data to the endpoint. For example, use the following command snippet:

{% code overflow="wrap" %}
```bash
curl -X POST http://localhost:3000/api/apps/public/0b57f89a-5753-4298-9695-caba6eb21e12/api \
-H "Content-Type: application/json" \
-d '{"Jack":"Hello :)", "Lucy":"Hi!"}'
```
{% endcode %}

It returns a response with the `messageId` similar to `{"messageId":"NNWbiDHbpa5Tn27XB"}`. The app bot also sends the message to the general channel as shown below:

![](<../../.gitbook/assets/image (20).png>)
