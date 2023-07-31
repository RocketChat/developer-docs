# Test Rocket.Chat

One of the most effective ways to contribute is by helping to test the Rocket.Chat core server code, as well as its web, desktop, and mobile applications. This document provides a guide on how to get involved in testing Rocket.Chat, ensuring its robustness and reliability for users worldwide.

### **Testing Core Server**

{% hint style="info" %}
**Prerequisites**&#x20;

* [Set up your development environment](../../getting-started/development-environment-setup.md)&#x20;
* Google Chrome Browser
{% endhint %}

### Getting Started

#### Start Meteor

Run meteor with the command below:

```
TEST_MODE=true meteor
```

To run the tests, the server **must** be started with the environment variable `TEST_MODE=true`. This will set all animations' duration to 0 and create an extra admin user with the login values:

```
_id: "rocketchat.internal.admin.test"
name: "RocketChat Internal Admin Test"
username: "rocketchat.internal.admin.test"
emails: "rocketchat.internal.admin.test@rocket.chat"
password: "rocketchat.internal.admin.test"
```

#### Run Tests

Once the server is running in the test mode, you can proceed to run the tests. This process requires opening another terminal window and executing the command below:

```
meteor npm run test
```

Contributing to Rocket.Chat by testing its core server code and applications is a valuable way to ensure the platform's stability and functionality. By following the steps outlined in this guide, you can play a crucial role in the ongoing development and improvement of Rocket.Chat. Your contribution will help maintain the platform's high standards, benefiting users around the globe.
