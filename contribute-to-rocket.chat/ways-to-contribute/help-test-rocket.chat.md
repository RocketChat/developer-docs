# Help Test Rocket.Chat

Thank you for your interest in contributing to Rocket.Chat. You can help in testing the Rocket.Chat core server code, testing our web, desktop, and mobile apps.

## Testing Core Server

[Set up your development environment](../../getting-started/rocket.chat-development-environment-setup.md) then continue.

### Requirements

* Google Chrome Browser

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

On another terminal window, run the test with the command below:

```
meteor npm run test
```
