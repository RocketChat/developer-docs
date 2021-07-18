# Omnichannel Livechat Endpoints

## Agent

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/agent.info/:rid/:token` | Retrieves the current omnichannel agent data | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/agent) |
| `livechat/agent.next/:token` | Retrieves the data of next available agent   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-agent/next-agent) |

## Configuration 

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/config` | Get LiveChat widget configuration info and additional visitor data. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-config) |

## Contacts

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `omnichannel/contact` | Registers a guest user as a new omnichannel contact | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/register-omnichannel-contact) |
| `omnichannel/contact` | Retrieves a contact information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-fetch-contact) |
| `omnichannel/contact.search` | Search a contact information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-contact/omnichannel-search-contact) |

## Custom Field

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/custom.field` | Send a custom field | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-a-livechat-custom-field) |
| `livechat/custom.fields` | Send an array of custom field | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/send-an-array-of-livechat-custom-fields) |
| `livechat/custom-fields` | Get a list of omnichannel custom fields | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/list-livechat-custom-fields) |
| `livechat/custom-fields/:_id` | Get info about a custom field | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/custom-fields/get-info-about-a-custom-field) |

## Message

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/message` | Send a new omnichannel message | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/livechat-send-new-message) |
| `livechat/message/:_id` | Retrieve a specific message  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/retrieve-a-livechat-message) |
| `livechat/message/:_id` | Update an omnichannel message | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/update-a-livechat-message) |
| `livechat/message/:_id` | Removes an omnichannel message | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/remove-a-livechat-message) |
| `livechat/messages.history/:rid` | Retrieve omnichannel messages history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-message/load-livechat-messages-history) |
| `livechat/messages` | Send multiple messages at once | Link |

## Offline Message

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/offline.message` | Sends an offline message when no agent is available  | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-offline-message) |

## Page Visited

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/page.visited` | post | Link |

## Room

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/room` | Get the omnichannel room data or open a new conversation. | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-info) |
| `livechat/room.close` | Close an omnichannel conversation | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-close) |
| `livechat/room.transfer` | Transfer an omnichannel conversation | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-transfer) |
| `livechat/room.forward` | Chatbot agent forwards the chat to a human agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/livechat-room-forward) |
| `livechat/room.visitor` | Updates room visitor's information | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-room/change-room-visitor) |

## Transcript

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/transcript` | Request a Livechat transcript | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transcript) |

## Transfer

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/transfer.history/:rid` | Retrieve the conversation transfer history | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/livechat-transfer) |

## Visitor

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/visitor` | Register a new visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/register-a-new-livechat-visitor) |
| `livechat/visitor/:token` | Retrieve a visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-livechat-endpoints/visitor/retrieve-a-visitor-data) |
| `livechat/visitor/:token` | delete | [Link](https://github.com/RocketChat/developer-docs/tree/416477aacf3193fe1c499552e2eebe39ad0c1878/api/rest-api/methods/livechat/methods/livechat/rooms.md) |
| `livechat/visitor/:token/room` | get |  |
| `livechat/visitor.status` | POST |  |



