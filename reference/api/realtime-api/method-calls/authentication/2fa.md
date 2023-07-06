# Two Factor Authentication

{% hint style="info" %}
To learn more about about Two Factor Authentication(2FA) in Rocket.Chat, see [two-factor-authentication.md](../../../../../rocket.chat/two-factor-authentication.md "mention").
{% endhint %}

## Call a method with 2FA

| Name                        | Requires Auth | Permission | Setting |
| --------------------------- | ------------- | ---------- | ------- |
| `callWithTwoFactorRequired` | Yes           |            |         |

### Payload Parameters

| Argument      | Example                                                                                         | Required            | Description                                               |
| ------------- | ----------------------------------------------------------------------------------------------- | ------------------- | --------------------------------------------------------- |
| **code**      | `56830`                                                                                         | Required            | The 2FA code                                              |
| **ddpMethod** | `pinMessage`                                                                                    | <p>Required<br></p> | The initial method for the request you're trying to make. |
| **method**    | `email`                                                                                         | Required            | The method of the 2FA, _for example -email_               |
| **params**    | `{ "_id": "298gMs93982Le9A7pZjo2D2iB", "rid": "64a1f373376181965ab77f54", "msg": "Whats 4*!" }` | Required            | An array of parameters used for the initial method;       |

### Example Call

```
{
    "msg": "callWithTwoFactorRequired"
    "code": "38290",
    "ddpMethod": "updateMessage",
    "id": "342",
    "method": "email",
    "params": [{
        "_id": "298gMs93982Le9A7pZjo2D2iB",
        "rid": "64a1f373376181965ab77f54",
        "msg": "Whats 4*!"
}]
        
}
```

{% hint style="info" %}
If the two factor was not accepted the **error** [`totp-invalid`](2fa.md#errors) will be returned;
{% endhint %}

## Errors

When a request that requires 2FA is made without a 2FA code, it returns a **TOTP-Require** error. The error also details the method of 2FA required ( email or authenticator app).

```javascript
{
  "msg": "result",
  "id": "1",
  "error": {
    "isClientSafe": true,
    "error": "totp-required",
    "reason": "TOTP Required",
    "details": {
      "method": "email",
      "codeGenerated": false,
      "codeCount": 1,
      "codeExpires": [
        "2019-12-31T22:05:22.159Z"
      ],
      "availableMethods": [
        "email"
      ]
    },
    "message": "TOTP Required [totp-required]",
    "errorType": "Meteor.Error"
  }
}
```

* **method**: The method selected by the server. It is useful to inform the user where to look for the code.
* **codeGenerated**: Email only. Used to inform if the code was generated or if there are tokens available already.
* **codeCount**: (optional) Email only. The number of available codes already sent via email.
* **codeExpires**: (optional) Email only. A list of expiration dates of the tokens.
* **availableMethods**: The list of available 2FA methods for Two Factor.  It is useful in deciding the method to use when making a request.

## Request a new email code

If the user didn't receive the 2FA code, you can request to send a new code via email by calling the DDP Method `sendEmailCode` passing the user's email or username. It's required to pass the email or username because this Method can be called when the user is not logged in.

### Response

* **success**: array of emails to where the code was sent;
* &#x20;**error-parameter-required:** The parameter `emailOrUsername` was not provided;
* **error-invalid-user:** The user was not found with the provided `emailOrUsername`;

### Example

```javascript
Meteor.call('sendEmailCode', emailOrUsername, (error, result) => {});
```

## Enabling the Two Factor via Email

It's possible to enable the email check by calling the Method `2fa:enable-email`.&#x20;

{% hint style="info" %}
The two factor via email will only work if the user has at least one verified email.
{% endhint %}

### Result

* **success**: **true** is returned;
* **error-not-authorized** if the user is not logged in;

### Example

```javascript
Meteor.call('2fa:enable-email', (error, result) => {});
```

## Disabling the Two Factor via Email

To disable the 2FA,  call the method `2fa:disable-email`.&#x20;

{% hint style="info" %}
This Method requires 2FA to be executed.
{% endhint %}

### Result

* **success**: **true** is returned;
* **error**: A [2FA error](2fa.md#errors) is returned;

### Example

```javascript
Meteor.call('2fa:disable-email', (error, result) => {});
```
