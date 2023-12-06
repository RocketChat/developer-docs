# REST Two Factor Authentication

{% hint style="info" %}
To learn more about Two Factor Authentication (2FA) in Rocket.Chat, see [two-factor-authentication.md](../../../../../rocket.chat/two-factor-authentication.md "mention") and [realtime-two-factor-authentication.md](../../../realtime-api/method-calls/authentication/realtime-two-factor-authentication.md "mention")
{% endhint %}

## Errors

When a call that requires 2FA is made, it returns an error type `totp-require`. The `details` object will list the method that has been required (email in this example) so it's possible to inform the user to check his email for the code.

* **method**: The method selected by the server. Useful to inform the user where to look for the code.
* **codeGenerated**: Email only. Used to inform if the code was generated or if there are tokens available already.
* **codeCount**: (optional) Email only. The number of available codes already sent via email.
* **codeExpires**: (optional) Email only. A list of expiration dates of the tokens.
* **availableMethods**: The list of available methods for 2FA. When calling an API it's possible to define the method to use.

```javascript
{
  "success": false,
  "error": "TOTP Required [totp-required]",
  "errorType": "totp-required",
  "details": {
    "method": "email",
    "codeGenerated": false,
    "codeCount": 1,
    "codeExpires": [
      "2020-01-02T13:06:42.408Z"
    ],
    "availableMethods": [
      "email"
    ]
  }
}
```

## Call an endpoint with 2FA

After receiving the error it's necessary to pass the informed code to the API. For that, we need to call the same endpoint and pass some new headers:

### Request headers

* **x-2fa-code**: (string) The code informed by the user.
* **x-2fa-method**: (string) The desired method to check the 2FA, usually the same from the error.

### Result

* If the 2FA was accepted, you get a successful authentication response.
* If the 2FA is not successful, the **error** `totp-invalid` will be returned.

```json
// Error example
{
  "success": false,
  "error": "TOTP Invalid [totp-invalid]",
  "errorType": "totp-invalid",
  "details": {
    "method": "email"
  }
}
```

## Request a new email code

If the user didn't receive the code, request the server to send a new code via email by calling the endpoint `users.2fa.sendEmailCode` via `POST` passing the user's email or username as the body. It's required to pass the email or username because this endpoint can be called when the user is not logged in.

### Request

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/users.2fa.sendEmailCode' \
```

### Body Parameters

* **sendEmailCode**: (string) The user's username or email.

### Result

* Success: **array of emails** to where the code was sent is returned.
* Errors:&#x20;
  * **error-parameter-required** if the parameter `emailOrUsername` was not provided.
  * **error-invalid-user** if the user was not found with the provided `emailOrUsername`.

## Handle password fallback

If an API request returns `TOTP Required` with a method _password_, then the API user's password is required to authenticate the request:

```json
// Error example
{
  "success":false,
  "error":"TOTP Required [totp-required]",
  "errorType":"totp-required",
  "details":{
    "method":"password",
    "codeGenerated":false,
    "availableMethods":[]
  }
}
```

### Request headers

The request must be submitted with two additional headers.

* **X-2fa-code**: (string) The API user's password sha256 hashed.
* **X-2fa-method**: `password`

### Request

```powershell
curl -H "X-Auth-Token: $YOUR_AUTH_TOKEN" \
     -H "X-User-Id: $YOUR_USER_ID" \
     -H "Content-type: application/json" \
     -H "X-2fa-code: $SHA_256_HASH_OF_API_USER_PASSWORD" \
     -H "X-2fa-method: password" \
     
     http://localhost:3000/api/v1/users.update \
     -d '{"userId": "SOME_USER_ID", 
          "data": { "requirePasswordChange": false }}'
```

## Enable 2FA via Email

Enable the email check by calling the following endpoint:&#x20;

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/users.2fa.enableEmail' \
```

Note that 2FA via email will only work if the user has at least one verified email.

### Result

* Success: `{success: true}` is returned.
* Error: `not-authorized` if the user is not logged in.

## Disable 2FA via Email

Disable the email check by calling the following endpoint:

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/users.2fa.disableEmail' \
```

Note that this endpoint requires 2FA authentication.

### Result

* Success: `{success: true}` is returned.
* Error: A 2FA verification error is returned.

For more user management endpoints, see [Users Endpoints](../user-management/users-endpoints/).
