# Testing the iFrame Authentication

After successfully[ configuring the iFrame authentication](../../../customize-and-embed/iframe-integration/configuring-iframe-auth/), it is crucial to test the setup to ensure its proper functioning. This guide provides a succinct overview of how to test the iFrame authentication in Rocket.Chat. Testing the iFrame authentication in Rocket.Chat involves using a test tool developed by the Rocket.Chat team. This test scenario is based on a localhost environment.

* **Step 1:** Download and start the _iframe-auth-example_ test service following the steps mentioned [here](https://github.com/RocketChat/iframe-auth-example). The test service code, which can be used as an example of how to set up the iFrame auth calls to Rocket.Chat, is [available for download](https://github.com/RocketChat/iframe-auth-example/blob/master/index.js). Once the test service is running, the iFrame authentication calls are executed.
* **Step 2**: The test involves configuring the Rocket.Chat server: **Administration > Workspace > Settings > Accounts > Iframe**&#x20;

![](../../../.gitbook/assets/84309416-78b60580-ab36-11ea-9777-f2c0138a9677.png)

* **Step 3**: and testing the iFrame service by calling the Rocket.Chat login URL (in this example, [http://localhost:3000\\](http://localhost:3000)_)_.&#x20;

![](../../../.gitbook/assets/2020-08-12\_10-58.png)

At this moment, the _iframe-auth-example_ service runs, and the iframe authentication calls are executed.

The test service code expects the login to be done with specific hardcoded credentials. \
`username: new-user`\
`password: new-users-passw0rd`

Change the `currentUsername` (line 105) to `true` so you can log in again with the same user. However, by changing the code, any user that already exists in Rocket.Chat can be used.

Further references can be found [here](https://github.com/RocketChat/Rocket.Chat.ReactNative/pull/2184).
