# Register Livechat Visitor

Register a visitor's information before creating a new Omnichannel room. You can set basic information such as name, phone, custom fields, and the initial department

<table><thead><tr><th width="163">HTTP Method</th><th width="296">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/visitor</code></td><td><code>no</code></td></tr></tbody></table>

## Body

<table><thead><tr><th width="216.33333333333331">Key</th><th width="248">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>visitor</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "visitor": { ... }</code></td><td>Enter the body parameters in the <code>visitor</code> object.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>erdsfdjs43828492</code></td><td>Enter a random unique string as the visitor token.</td></tr><tr><td><code>name</code></td><td><code>John Doe</code></td><td>Visitor's name.</td></tr><tr><td><code>email</code></td><td><code>john.doe@email.com</code></td><td>Visitor's email ID.</td></tr><tr><td><code>department</code></td><td><code>Support</code></td><td>The department that the visitor wants to register to.</td></tr><tr><td><code>phone</code></td><td><code>+37265783468</code></td><td>Visitor's phone number.</td></tr><tr><td><code>username</code></td><td><code>kim.jane</code></td><td>The agent's user name.</td></tr><tr><td><code>custom fields: key, value, overwite</code></td><td><p><code>"customFields": [{ "key": "address", "value": "Rocket.Chat street",</code> </p><p><code>"overwrite": true }]</code></p></td><td>Enter the custom field key, value, and whether you want to overwrite this information.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/visitor' \
--header 'Content-Type: application/json' \
--data-raw '{
  "visitor": {
    "name": "Livechat Visitor",
    "email": "visitor@rocket.chat",
    "department": "Support",
    "token": "iNKE8a6k6cjbqWhWd",
    "phone": "55 51 5555-5555",
    "customFields": [{
      "key": "address",
      "value": "Rocket.Chat street",
      "overwrite": true
    }]
  }
}'
```
{% endcode %}

## Example Response

```json
{
    "visitor": {
        "_id": "642fc15452492a08c3a756de",
        "username": "guest-19",
        "status": "online",
        "ts": "2023-04-07T07:08:04.375Z",
        "_updatedAt": "2023-11-03T08:23:23.449Z",
        "name": "Livechat Visitor",
        "phone": [
            {
                "phoneNumber": "55 51 5555-5555"
            }
        ],
        "token": "iNKE8a6k6cjbqWhWd",
        "visitorEmails": [
            {
                "address": "visitor@rocket.chat"
            }
        ],
        "department": "64181a0728384134ed600dcc"
    },
    "success": true
}
```

After registering the visitor, [create the Omnichannel room](../livechat-room/get-or-create-livechat-rooms.md) using the same token used in this endpoint.
