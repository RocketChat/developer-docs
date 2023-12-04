# Create Voice Channel Visitor

<table><thead><tr><th width="163">HTTP Method</th><th width="314">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/visitor</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="216.33333333333331">Key</th><th width="248">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>visitor</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "visitor": { ... }</code></td><td>Enter the body parameters in the <code>visitor</code> object.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>erdsfdjs43828492</code></td><td>Enter a random unique string as the visitor token.</td></tr><tr><td><code>name</code></td><td><code>John Doe</code></td><td>Visitor's name.</td></tr><tr><td><code>email</code></td><td><code>john.doe@email.com</code></td><td>Visitor's email ID.</td></tr><tr><td><code>department</code></td><td><code>Support</code></td><td>The department that the visitor wants to register to.</td></tr><tr><td><code>phone</code></td><td><code>+37265783468</code></td><td>Visitor's phone number.</td></tr><tr><td><code>username</code></td><td><code>kim.jane</code></td><td>The agent's user name.</td></tr><tr><td><code>custom fields: key, value, overwite</code></td><td><p><code>"customFields": [{ "key": "address", "value": "Rocket.Chat street",</code> </p><p><code>"overwrite": true }]</code></p></td><td>Enter the custom field key, value, and whether you want to overwrite this information.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request POST 'localhost:3000/api/v1/livechat/visitor' \
--header 'Content-Type: application/json' \
--data-raw '{
    "visitor": {
        "token": "867ad6a09fc4af29f6f1f2a9cf1deaba"
    }
}'
```

## Example Response

```json
{
    "visitor": {
        "_id": "b3c7SMriL729R3J8w",
        "username": "guest-2",
        "status": "online",
        "ts": "2022-06-29T06:05:01.392Z",
        "_updatedAt": "2022-06-29T06:05:01.408Z",
        "token": "867ad6a09fc4af29f6f1f2a9cf1deaba"
    },
    "success": true
}
```
