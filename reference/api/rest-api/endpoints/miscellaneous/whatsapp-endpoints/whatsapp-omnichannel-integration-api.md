---
description: WhatsApp Business Integration for Rocket.Chat
---

# WhatsApp Business Omnichannel Integration

Integrating Whatsapp business in your Rocket.Chat workspace offers valuable enhancements to simplify your business communication workflows. The [Whatsapp business integration](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace/rocket.chat-public-apps-guides/omnichannel-apps/whatsapp-cloud-app) allows you to send template messages to a targeted user.

You can send a Whatsapp template message from your workspace via the following methods:

1. **Sending template messages via endpoints**: Refer to the [Send a Template WhatsApp Message](../../marketplace-apps/whatsapp-endpoints/send-a-template-whatsapp-message.md) API endpoint.
2. **Slash commands and UI**: Send the template message in a more user-friendly way using the GUI form. To trigger the GUI, open a WhatsApp contact room and run the `/whatsapp send-template`command. This command opens up a modal where you can select the following:

* The `Template` you wish to send,
* The `Language` you wish to send the template in,
* And also substitute `parameters` within the message, if present

{% hint style="info" %}
If parameters are present within the template message, kindly ensure you substitute all of them before sending the message. Failure to do so will result in an error.
{% endhint %}

**Getting the status of messages sent**

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

In conclusion, the ability to send template messages through WhatsApp Business Integration enables businesses to maintain a consistent and professional communication approach with their audience.&#x20;
