# Testing the iFrame Authentication

After you've successfully completed [configuring-iframe-auth](../../../customize-and-embed/iframe-integration/configuring-iframe-auth/ "mention"), it's essential to confirm its functionality by testing. This guide offers a concise outline for testing iFrame authentication within Rocket.Chat. The process entails utilizing a test tool created by the Rocket.Chat team. The test service can be used as an example of how to set up the iFrame auth calls to Rocket.Chat.

{% hint style="warning" %}
This test tool is designed for your localhost enviroment.
{% endhint %}

&#x20;To test your iFrame auth configuration,

* Clone the GitHub repository for the [iframe-auth-example](https://github.com/RocketChat/iframe-auth-example) test service. Navigate to the project directory and run these commands to start the project:

```
npm install
npm start
```

{% hint style="info" %}
The project is running on port 3030.
{% endhint %}

* On your Rocket.Chat workspace, navigate to **Administration > Workspace > Settings > Accounts > Iframe.** Toggle on **Enabled.** Add the **iFrame URL** and **API URL**.

![](../../../.gitbook/assets/84309416-78b60580-ab36-11ea-9777-f2c0138a9677.png)

* Navigate to the login page of the test project, which is accessible at _localhost:3030/login_ for this example. Proceed to test the iFrame auth by submitting a **username** and **password.**

{% hint style="warning" %}
The test project requires the following hardcoded credentials for login:&#x20;

Username: `new-user`&#x20;

Password: `new-users-passw0rd`

Change the `currentUsername` to '**true**' at line 105 in the index.js to enable re-login with the same user. Note that modifying the code allows any existing Rocket.Chat user to be used.

To learn more, see this [pull request](https://github.com/RocketChat/Rocket.Chat.ReactNative/pull/2184).
{% endhint %}

* Once the _iframe-auth-example_ service runs, the iframe authentication calls are executed. It returns unauthorized if the credentials are not valid.

By adhering to the outlined steps and leveraging the provided test tool, you can confirm the successful integration of iframe authentication into your Rocket.Chat setup.
