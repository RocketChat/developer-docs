# Send a WhatsApp Template Message

Send template messages via WhatsApp to targeted contacts directly from your workspace using this endpoint. It supports only [WhatsApp Cloud App](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-cloud-app) and [WhatsApp Sandbox App](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-sandbox).

{% hint style="info" %}
In [WhatsApp sandbox](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-sandbox), there are only three pre-defined message templates available for use. It's not possible to create new templates or modify the existing ones. Refer to the the [official documentation](https://docs.360dialog.com/docs/waba-messaging/sandbox#id-5.-send-a-template-message-optional) for more details.
{% endhint %}

<table><thead><tr><th width="229">HTTP Method</th><th>URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td>Navigate to the <strong>Details</strong> tab of the <strong>App Info page</strong> to get the template message URL for the WhatsApp app in your workspace. <br>For example, <br><code>http://{rocketchat-workspace}/api/apps/private/{application-id}/templateMessage</code></td><td><a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/authentication-endpoints">no</a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="260.3333333333333">Key</th><th>Description</th><th>Example Value</th></tr></thead><tbody><tr><td><code>phoneNumbers</code><mark style="color:red;"><code>*</code></mark></td><td>Recipient WhatsApp IDs where you want to send the template message. <br><br>Note that you can validate a WhatsApp id from <a href="https://developers.facebook.com/docs/whatsapp/api/contacts">here</a>.</td><td><code>"phoneNumbers": [ "+917785887264", "+551452001478" ]</code></td></tr><tr><td><code>connectedWhatsAppNo</code><mark style="color:red;"><code>*</code></mark></td><td>The WhatsApp Number from which you want to send this template message.</td><td><code>"connectedWhatsAppNo": "+565412001234"</code></td></tr><tr><td><code>targetAgent</code></td><td>Username of the agent you want to transfer the chat to when the WhatsApp user replies.</td><td><code>"targetAgent": "murtaza98"</code></td></tr><tr><td><code>targetDepartment</code></td><td>Department name or ID where you want to transfer the chat to when the WhatsApp user replies.</td><td><code>"targetDepartment": "SalesDepartment"</code></td></tr><tr><td><code>template</code><mark style="color:red;"><code>*</code></mark></td><td>Provide information about the template message you wish to send.<br>It is the same as <a href="https://developers.facebook.com/docs/whatsapp/api/messages/message-templates#the-template-object">WhatsApp-template-object</a>.</td><td>Refer to the example in <a data-mention href="../../../../../../omnichannel/whatsapp-business-template-messages.md#sending-whatsapp-template-messages-from-your-workspace">#sending-whatsapp-template-messages-from-your-workspace</a></td></tr></tbody></table>

{% hint style="info" %}
We strongly recommend including the `+` prefix for all phone numbers in the payload. While you _can_ submit numbers without the leading `+` sign, we have encountered cases where WhatsApp will return an invalid response despite the number being in use.
{% endhint %}

## Example Body

```json
{
    "phoneNumbers": [
        "+917785887264", "+551452001478"
    ],
    "connectedWhatsAppNo": "+565412001234",
    "targetAgent": "murtaza98",
    "targetDepartment": "SalesDepartment",
    "template": {
        "namespace": "your-namespace",
        "name": "your-template-name",
        "language": {
            "code": "your-language-and-locale-code",
            "policy": "deterministic"
        },
        "components": [
            {
                "type": "header",
                "parameters": [
                    {
                        "type": "text",
                        "text": "your-text-string"
                    }
                ]
            },
            {
                "type": "body",
                "parameters": [
                    {
                        "type": "text",
                        "text": "your-text-string"
                    },
                    {
                        "type": "text",
                        "text": "your-text-string"
                    }
                ]
            },
            {
                "type": "footer",
                "parameters": [
                    {
                        "type": "text",
                        "text": "your-text-string"
                    }
                ]
            },
        ]
    }
}
```

## **Sample Call**

{% code overflow="wrap" %}
```powershell
curl --location --request POST 'http://localhost:3000/api/apps/public/085b7345-53e7-498c-adcb-d909e11f8100/templateMessage' \
--header 'Content-Type: application/json' \
--data-raw '{
    "phoneNumbers": [
        "+917738772967"
    ],
  "connectedWhatsAppNo": "+565412001234",
    "targetAgent": "murtaza98",
    "targetDepartment": "SalesDepartment",
    "template": {
        "namespace": "aa498c38_6c0c_448d_a652_38f5d33b8c7f",
        "name": "sales_welcome_template",
        "language": {
            "code": "en",
            "policy": "deterministic"
        }
    }
}'
```
{% endcode %}

## Responses

<table><thead><tr><th width="338">Success Response</th><th>Error Response</th></tr></thead><tbody><tr><td><strong>Code:</strong> 200<br><strong>Content:</strong> <code>{ success: true }</code></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Too many phone numbers! Please make sure that phoneNumbers are &#x3C;= 250" }</code></td></tr><tr><td><strong>Code:</strong> 200<br><strong>Content:</strong><br><code>{ "success": true, "invalidContacts": [ "917738772967" ] }</code></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "No Agent found with username abc98" }</code></td></tr><tr><td></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "No Department found with id/Name SalesDepartment" }</code></td></tr><tr><td></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Error! Missing "connectedWhatsAppNo" field within the request" }</code></td></tr><tr><td></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Connected WhatsApp Number (connectedWhatsAppNo) i.e. 565412001234 is not a valid WhatsApp contact. Contact Status is invalid" }</code></td></tr><tr><td></td><td><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Error! Connected WhatsApp Number (connectedWhatsAppNo) i.e. 565412001234 has not been registered yet on Rocket.Chat. Please goto #omnichannel-whatsapp-setup channel and connect this WhatsApp number first there before sending this request again." }</code></td></tr><tr><td></td><td><strong>Code:</strong> 500 Internal Server Error<br><strong>Content:</strong><br><code>{ "success": false, error : "Error occurred while processing request. Details: [Error Details]" }</code></td></tr></tbody></table>
