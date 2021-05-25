---
description: WhatsApp Business API Integration for Rocket.Chat
---

# WhatsApp Integration

## Getting started with Template messages

The WhatsApp app allows you to send template messages to a target user.

In order to send a template message, you have 2 options

1. Via the endpoint
   * REST API Documentation for this endpoint can be found [here](https://github.com/RocketChat/Apps.WhatsApp/blob/main/docs/TemplateMessage.md)
2. Via the Slash Command and UI
   * You can send the template message in a more user-friendly way using the GUI form.
   * To trigger the GUI, open a WhatsApp contact room and run the following command

     > `/whatsapp send-template`

   * This will open up a modal, where you can select
     * The `Template` you wish to send,
     * The `Language` you wish to send the template in,
     * And also substitute `parameters` within the message, if present.

       > Note, If parameters \(i.e eg \) are present withing the template message, please make sure that you substitute all of them before sending the message. Failure to do so will result in an error.

A video demonstration of the above feature is available here: [![Watch the video](https://img.youtube.com/vi/TMNZ8HjGx-M/maxresdefault.jpg)](https://youtu.be/TMNZ8HjGx-M)

## Getting status of messages sent

To receive real-time status updates for outbound messages, you can choose to set a _Message Status Endpoint URL_. The app will send a request to this URL each time your message status changes to one of the following: queued, failed, sent, delivered, read, or if some error occurs.

You can set the _Message Status Endpoint URL_ in the Apps Settings.

Following is the payload format you will receive on the endpoint

| **Field Name** | **Type** | **Description** |
| :---: | :---: | :---: |
| msId | String or undefined | Message Id. |
| message | String | Text message |
| mobileNo | String | Phone number of WhatsApp user to which you had sent the message |
| connectedWhatsAppNo | String | Your connected WhatsApp Number from which you had sent the message to user |
| MessageStatus | String | Status of message - sent, delivered, read, failed, deleted |
| ErrorDetails | Optional   Type: String or WhatsApp error format | Errors from template messages will be shown here |
| type | String | `Template-Message` or `Regular-Message` |
| timestamp | String | Timestamp of request |

