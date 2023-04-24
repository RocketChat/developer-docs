# Iframe integration: Sending commands

When integrating an iframe into Rocket.Chat, you can also send commands to the embedded content using the `postMessage` Rocket.Chat API. It allows you to interact with the content in real time and perform various actions.&#x20;

## Available commands

| Command                 | Params             | Description                               |
| ----------------------- | ------------------ | ----------------------------------------- |
| go                      | - `path` string    | Change url                                |
| login-with-token        | - `token` string   | Allow login with token                    |
| call-custom-oauth-login | - `service` string | Allow login via oauth methods             |
| set-user-status         | - `status` string  | Set the status of the user                |
| logout                  |                    | Log the user out of their current session |



Here is an example of how to send a command through a Rocket.Chat iframe:

```javascript
document.querySelector('iframe').contentWindow.postMessage({
  externalCommand: 'go',
  path: '/admin/General'
}, '*')
```

Another useful example is setting user status in an iframe embedded in Rocket.Chat :&#x20;

```javascript
document.querySelector('iframe').contentWindow.postMessage({
  externalCommand: 'userSetStatus',
  status: 'away'
}, '*')
```



