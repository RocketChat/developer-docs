---
description: Send a template message
---

# Template Whatsapp message

| URL                                                                                                                                                                            | **Method** | **Input Data Format** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------------- |
| <p>REST API URL can be found on Apps Page<br>Sample Url for eg:<br><code>http://localhost:3000/api/apps/public/30bf52a3-d65b-4ab1-9b11-7cfdddf1ef29/templateMessage</code></p> | `POST`     | `JSON`                |

### Request structure

```
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

### Parameters

| **Param Name**        | **Param Type**                                                                                                                       | **Description**                                                                                                                                                                   | **Dependency** | **Example**                                            |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ------------------------------------------------------ |
| `phoneNumbers`        | Array of String                                                                                                                      | Recipient WhatsApp Id(s) where you want to send the template message. Note you can validate a WhatsApp id from [here](https://developers.facebook.com/docs/whatsapp/api/contacts) | Required       | `"phoneNumbers": [ "+917785887264", "+551452001478" ]` |
| `connectedWhatsAppNo` | String                                                                                                                               | The WhatsApp Number from which you want to send this template message                                                                                                             | Required       | `"connectedWhatsAppNo": "+565412001234"`               |
| `targetAgent`         | String                                                                                                                               | Username of the targetAgent you wish to transfer the chat to when the WhatsApp user replies back                                                                                  | Optional       | `"targetAgent": "murtaza98"`                           |
| `targetDepartment`    | String                                                                                                                               | Department Name or Id where you wish to transfer the chat to when the WhatsApp user replies back                                                                                  | Optional       | `"targetDepartment": "SalesDepartment"`                |
| `template`            | Same as [WhatsApp-template-object](https://developers.facebook.com/docs/whatsapp/api/messages/message-templates#the-template-object) | Provide information about the template message you wish to send                                                                                                                   | Required       | Please refer to the template property in above examp   |

| :warning: | We strongly recommend including the '+' prefix for the all PhoneNumbers in the payload. While you _can_ submit numbers without the leading '+' we have encountered cases where WhatsApp will return 'invalid' despite the number being in use. |
| :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

## **Sample Call**

**Curl**

```
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

**HTTP**

```
  POST /api/apps/public/085b7345-53e7-498c-adcb-d909e11f8100/templateMessage HTTP/1.1
  Host: localhost:3000
  Content-Type: application/json
  Content-Length: 312

  {
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
  }
```

## Response

| Success Response                                                                                                                          | Error Response                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><strong>Code:</strong> 200<br><strong>Content:</strong> <code>{ success: true }</code></p>                                             | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Too many phone numbers! Please make sure that phoneNumbers are &#x3C;= 250" }</code></p>                                                                                                                                                                           |
| <p><strong>Code:</strong> 200<br><strong>Content:</strong><br><code>{ "success": true, "invalidContacts": [ "917738772967" ] }</code></p> | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "No Agent found with username abc98" }</code></p>                                                                                                                                                                                                                   |
|                                                                                                                                           | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "No Department found with id/Name SalesDepartment" }</code></p>                                                                                                                                                                                                     |
|                                                                                                                                           | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Error! Missing "connectedWhatsAppNo" field within the request" }</code></p>                                                                                                                                                                                        |
|                                                                                                                                           | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Connected WhatsApp Number (connectedWhatsAppNo) i.e. 565412001234 is not a valid WhatsApp contact. Contact Status is invalid" }</code></p>                                                                                                                         |
|                                                                                                                                           | <p><strong>Code:</strong> 400 BAD REQUEST<br><strong>Content:</strong><br><code>{ "success": false, error: "Error! Connected WhatsApp Number (connectedWhatsAppNo) i.e. 565412001234 has not been registered yet on Rocket.Chat. Please goto #omnichannel-whatsapp-setup channel and connect this WhatsApp number first there before sending this request again." }</code></p> |
|                                                                                                                                           | <p><strong>Code:</strong> 500 Internal Server Error<br><strong>Content:</strong><br><code>{ "success": false, error : "Error occurred while processing request. Details: [Error Details]" }</code></p>                                                                                                                                                                         |

## \*\*\*\*
