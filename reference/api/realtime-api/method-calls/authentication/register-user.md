# Register User

Register a user to your workspace.

## Payload Parameters

| Argument | Example         | Required | Description               |
| -------- | --------------- | -------- | ------------------------- |
| `email`  | `test@test.com` | Required | The email of the channel. |
| `pass`   | `["rocket.12"]` | Required | The password              |
| `name`   | `Test`          | Required | The name of the account.  |

## Example Call

```javascript
{
    "msg": "method",
    "method": "registerUser",
    "id":"482",
    "params": [{
        "email": "test@tes1t.com",
        "pass": "test31457",
        "name": "new te1st",
        "secretURL": "" 
        }]
	
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "482",
    "result": "3Dw26TXWxvi8gwfgM"
}
```

## Errors

If there are any errors during registration, here is a sample response format to expect:

```javascript
{
    "msg": "result",
    "id": "42",
    "error": {
        "error": 403,
        "reason": "...",
        "message": "... [403]",
        "errorType": "Meteor.Error"
    }
}
```

### Possible errors

```
"reason": "error-user-registration-disabled",
"message": "User registration is disabled [403]",

"reason": "error-user-registration-secret",
"message": "User registration is only allowed via Secret URL [403]",

"reason": "error-invalid-customfield-json",
"message": "Invalid JSON for Custom Fields [403]",
```

#### Custom Fields related

```
"reason": "error-user-registration-custom-field",
"message": "Field ${ fieldName } is required [403]",

"reason": "error-user-registration-custom-field",
"message": "Value for field ${ fieldName } is invalid [403]",

"reason": "error-user-registration-custom-field",
"message": "Max length of field ${ fieldName } ${ field.maxLength } [403]",

"reason": "error-user-registration-custom-field",
"message": "Min length of field ${ fieldName } ${ field.minLength } [403]",
```

## Accounts\_CustomFields

{% hint style="info" %}
You can use `customFields` as extra fields for user registration.
{% endhint %}

To register with custom fields, add  `Accounts_CustomFields` encoded as JSON:

```javascript
{
    "msg": "method",
    "method": "registerUser",
    "id":"482",
    "params": [{
        "email": "test@tes1t.com",
        "pass": "test31457",
        "name": "new te1st",
        "secretURL": "" ,
	"Accounts_CustomFields": {
    "role": {
        "type": "select",
        "defaultValue": "student",
        "options": ["teacher", "student"],
        "required": true,
        "modifyRecordField": {
            "array": true,
            "field": "roles"
        }
    },
    "twitter": {
        "type": "text",
        "required": true,
        "minLength": 2,
        "maxLength": 10
    }
}
    }]
}
```
