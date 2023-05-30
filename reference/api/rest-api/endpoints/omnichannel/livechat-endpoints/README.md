# Livechat Endpoints

## Agent

| Url                               | Short Description                              | Details Page                                                                                                                                |
| --------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/agent.info/:rid/:token` | Retrieves the current omnichannel agent data   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/agent)      |
| `livechat/agent.next/:token`      | Retrieves the data of the next available agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/next-agent) |

## Configuration

| Url               | Short Description                                                         | Details Page                                                                                                                      |
| ----------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/config` | Retrieves LiveChat widget configuration info and additional visitor data. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-config) |

## Contacts

| Url                          | Short Description                                   | Details Page                                                                                                                                                    |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `omnichannel/contact`        | Registers a guest user as a new omnichannel contact | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/register-omnichannel-contact) |
| `omnichannel/contact`        | Retrieves a contact information                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-fetch-contact)    |
| `omnichannel/contact.search` | Searches a contact information                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-search-contact)   |

## Custom Field

| Url                           | Short Description                             | Details Page                                                                                                                                                            |
| ----------------------------- | --------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/custom.field`       | Sends a custom field                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-a-livechat-custom-field)            |
| `livechat/custom.fields`      | Sends an array of custom field                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-an-array-of-livechat-custom-fields) |
| `livechat/custom-fields`      | Retrieves a list of omnichannel custom fields | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/list-livechat-custom-fields)             |
| `livechat/custom-fields/:_id` | Retrieves info about a custom field           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/get-info-about-a-custom-field)           |

## Message

| Url                              | Short Description                      | Details Page                                                                                                                                                      |
| -------------------------------- | -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/message`               | Sends a new omnichannel message        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/livechat-send-new-message)      |
| `livechat/message/:_id`          | Retrieves a specific message           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/retrieve-a-livechat-message)    |
| `livechat/message/:_id`          | Updates an omnichannel message         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/update-a-livechat-message)      |
| `livechat/message/:_id`          | Removes an omnichannel message         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/remove-a-livechat-message)      |
| `livechat/messages.history/:rid` | Retrieves omnichannel messages history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/load-livechat-messages-history) |
| `livechat/messages`              | Sends array of messages                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-message/send-an-array-of-messages)                            |

## Offline Message

| Url                        | Short Description                                   | Details Page                                                                                                                               |
| -------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/offline.message` | Sends an offline message when no agent is available | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-offline-message) |

## Page Visited

| Url                     | Short Description                                                    | Details Page                                                                                                                                      |
| ----------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/page.visited` | Retrieves the pages your omnichannel user navigated on your website. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-page-visited/send-visitor-navigation-history) |

## Room

| Url                      | Short Description                                                 | Details Page                                                                                                                                           |
| ------------------------ | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/room`          | GetRetrievesthe omnichannel room data or open a new conversation. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-info)     |
| `livechat/room.close`    | Closes an omnichannel conversation                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-close)    |
| `livechat/room.transfer` | Transfers an omnichannel conversation                             | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-transfer) |
| `livechat/room.forward`  | Chatbot agent forwards the chat to a human agent                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-forward)  |
| `livechat/room.visitor`  | Updates room visitor's information                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/change-room-visitor)    |

## Transcript

| Url                   | Short Description              | Details Page                                                                                                                          |
| --------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transcript` | Requests a Livechat transcript | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transcript) |

## Transfer

| Url                              | Short Description                           | Details Page                                                                                                                        |
| -------------------------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `livechat/transfer.history/:rid` | Retrieves the conversation transfer history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transfer) |

## Visitor

| Url                            | Short Description                        | Details Page                                                                                                                                                 |
| ------------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `livechat/visitor`             | Registers a new visitor                  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/register-a-new-livechat-visitor)    |
| `livechat/visitor/:token`      | Retrieves a visitor                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/retrieve-a-visitor-data)            |
| `livechat/visitor/:token`      | Deletes a visitor                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/delete-a-visitor)                   |
| `livechat/visitor/:token/room` | Retrieves open conversation of a visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/get-open-conversation-of-a-visitor) |
| `livechat/visitor.status`      | Sets visitor status                      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/set-visitor-status)                 |
