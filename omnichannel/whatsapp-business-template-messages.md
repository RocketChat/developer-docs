# WhatsApp Business Template Messages

Integrating Whatsapp business in your Rocket.Chat workspace offers valuable enhancements to simplify your business communication workflows. The WhatsApp business integration allows you to send template messages to targeted contacts from your workspace.

Template messages on WhatsApp serve as a proactive means for organizations to engage with their WhatsApp contacts. These messages can be related to appointment reminders, delivery updates, issue resolution, or payment updates. They also act as notifications, encouraging users to respond and kickstart conversations to foster interaction between organizations and their audiences. Kindly refer the official documentation for more details on [Whatsapp Template Messages](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/).

#### **Creating Template Messages on Your WhatsApp Business Account**

You need to have template messages on your WhatsApp business account before you can send them to contacts from your Rocket.Chat workspace.

{% hint style="warning" %}
Before you proceed, refer to the [Meta Template Guide](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/) for a comprehensive understanding of template messages.
{% endhint %}

In this guide, we'll be creating a simple shipping reminder template message. To create the template message,

* Go to your **Business Account** and navigate to **WhatsApp Manager.**
* Navigate to **Account tools > Message templates** and click **Create template**.
* Add the **category**, **name**, and **language** of the template message.
  * **Category**: Select **Utility** for this example guide.
  * **Name**: Add a **name** for the template message.
  * **Language**: Select **English** for this example guide.
* Click **Continue**.
* For this example guide, add this simple text in the **Body** : _"Your package has been shipped. It will be delivered in \{{1\}} business days."_
* Put a random integer in the **Samples for body content.**
* Click **Submit.**

The template message is now sent for review. Once it has been approved, you can now start [sending template messages to contacts from your workspace](whatsapp-business-template-messages.md#sending-whatsapp-template-messages-from-your-workspace).

{% hint style="info" %}
Visit this[ quick guide ](https://web.facebook.com/business/help/2055875911147364?id=2129163877102343&\_rdc=1&\_rdr)to learn more about **creating WhatsApp template messages**.
{% endhint %}

#### Sending WhatsApp template messages from your workspace

Once you've created template messages in your WhatsApp Business Account, you can send them to targeted contacts within your workspace using any WhatsApp App available on the Rocket.Chat marketplace.

To send a WhatsApp template message from your workspace, use any of the following methods:

1.  **Sending template messages via endpoint**: Refer to the [Send a Template WhatsApp Message](../reference/api/rest-api/endpoints/marketplace-apps/whatsapp-endpoints/send-a-template-whatsapp-message.md) API endpoint. Below is a sample JSON body parameter for using the example template [created earlier](whatsapp-business-template-messages.md#creating-template-messages-on-your-whatsapp-business-account) to send a template message via API:

    ```json
    {
        "phoneNumbers": [
            "2228105035435"
        ],
        "connectedWhatsAppNo": "104979685899299",
        "template": {
            "name": "ship",
            "language": {
                "code": "en",
                "policy": "deterministic"
            },
            "components": [
                {
                    "type": "body",
                    "parameters": [
                        {
                            "type": "text",
                            "text": "20"
                        }
                    ]
                }
            ]
        }
    }
    ```
2. **Slash commands and UI**: Send the template message using the GUI form in your workspace. To trigger the GUI, open a WhatsApp contact room and run the respective `send-template` command for the WhatsApp app.
   * [WhatsApp Sandbox](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-sandbox): Run the `/whatsapp-sandbox send-template`  command in the room. A pop-up modal is displayed prompting you to select the template name, language and other required details for the selected template. Click **Confirm** to send the template message to the sandbox number. Visit the [official documentation](https://docs.360dialog.com/docs/waba-messaging/sandbox#id-5.-send-a-template-message-optional) to learn more about the available WhatsApp Sandbox template messages.

{% hint style="info" %}
* If your template message includes parameters, make sure to replace all of them with the appropriate information before sending. Failure to do so may lead to an error.
* Sending template messages on the[ WhatsApp Cloud App](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-cloud-app) is exclusively available via the API endpoint.
* In [WhatsApp Sandbox](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-sandbox), there are only three pre-defined message templates available for use. It's not possible to create new templates or modify the existing ones. Refer to the the [official documentation](https://docs.360dialog.com/docs/waba-messaging/sandbox#id-5.-send-a-template-message-optional) for more details.
{% endhint %}

#### **Getting the status of messages sent**

To receive real-time status updates for outbound messages, navigate to the **Settings** tab of the Whatsapp App and set the _**Message Status Endpoint URL**_. The app sends a request to this URL each time your message status changes to one of the following: **queued**, **failed**, **sent**, **delivered**, **read**, or if some error occurs.

The table below highlights the payload format you will receive on the endpoint.

|    **Field Name**   |                         **Type**                         |                               **Description**                              |
| :-----------------: | :------------------------------------------------------: | :------------------------------------------------------------------------: |
|         msId        |                    String or undefined                   |                                 Message Id.                                |
|       message       |                          String                          |                                Text message                                |
|       mobileNo      |                          String                          |       Phone number of WhatsApp user to which you had sent the message      |
| connectedWhatsAppNo |                          String                          | Your connected WhatsApp Number from which you had sent the message to user |
|    MessageStatus    |                          String                          |         Status of message - sent, delivered, read, failed, deleted         |
|     ErrorDetails    | <p>Optional<br>Type: String or WhatsApp error format</p> |              Errors from template messages will be shown here              |
|         type        |                          String                          |                   `Template-Message` or `Regular-Message`                  |
|      timestamp      |                          String                          |                            Timestamp of request                            |

In conclusion, the ability to send template messages through WhatsApp Business Integration enables businesses to maintain a consistent and professional communication approach with their audience.
