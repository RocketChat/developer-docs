# Message

The message object is the very soul of a conversation. It encapsulates all the information needed in order to represent a single entry on a message list.

Messages are stored in the `rocketchat_message` collection on MongoDB.

The `IMessage` interface represents the structure of a message object in the Rocket.Chat It defines the properties and their types that can be associated with a message sent. You can check the `IMessage` interface here.

{% embed url="https://github.com/RocketChat/Rocket.Chat/blob/develop/packages/core-typings/src/IMessage/IMessage.ts" %}

<table><thead><tr><th width="306">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>r</code></td><td>Room name changed</td></tr><tr><td><code>au</code></td><td>User added by</td></tr><tr><td><code>ru</code></td><td>User removed by</td></tr><tr><td><code>ul</code></td><td>User left</td></tr><tr><td><code>ult</code></td><td>User left team</td></tr><tr><td><code>uj</code></td><td>User joined channel</td></tr><tr><td><code>ujt</code></td><td>User joined team</td></tr><tr><td><code>ut</code></td><td>User joined conversation</td></tr><tr><td><code>rm</code></td><td>Message removed</td></tr><tr><td>added-user-to-team</td><td>Added user to team</td></tr><tr><td>removed-user-from-team</td><td>Removed user from team</td></tr><tr><td>user-muted</td><td>User muted by</td></tr></tbody></table>

## Message Object

<details>

<summary>Example Object</summary>

```json
{
  "_id": "8gMsLe9ApZjo2D2iB",
  "rid": "EhpNtqqrMXT4QWk3z",
  "msg": "This meesage is from Rocket.Chat.",
  "ts": {
    "$date": "2023-02-09T13:35:59.484Z"
  },
  "u": {
    "_id": "rYhzFRd2QZjNwAAXX",
    "username": "rodriq",
    "name": "Rodriq"
  },
  "_updatedAt": {
    "$date": "2023-02-09T13:40:47.334Z"
  },
  "urls": [],
  "mentions": [],
  "channels": [],
  "md": [
    {
      "type": "PARAGRAPH",
      "value": [
        {
          "type": "PLAIN_TEXT",
          "value": "This meesage is from "
        },
        {
          "type": "LINK",
          "value": {
            "src": {
              "type": "PLAIN_TEXT",
              "value": "//Rocket.Chat."
            },
            "label": {
              "type": "PLAIN_TEXT",
              "value": "Rocket.Chat."
            }
          }
        }
      ]
    }
  ],
  "editedAt": {
    "$date": "2023-02-09T13:40:47.303Z"
  },
  "editedBy": {
    "_id": "rYhzFRd2QZjNwAAXX",
    "username": "rodriq"
  }
}
```

</details>

### Fields

The message object contains these fields.

| \_id            | string                                   | The unique identifier for the message.                                                                                                                                                                                                               |
| --------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rid             | string                                   | The unique id for the room. This will identify the room that the message belongs to. Example: '`GENERAL`'                                                                                                                                            |
| msg             | string                                   | The content of the message.                                                                                                                                                                                                                          |
| tmid            | string                                   | The ID of the thread where the message belongs to.                                                                                                                                                                                                   |
| tshow           | boolean                                  | Indicates whether the thread should be shown.                                                                                                                                                                                                        |
| ts              | Date                                     | A timestamp of when the message was created. (The date of creation on client)                                                                                                                                                                        |
| mentions        | Array of objects                         | An array of user mentions within the message. Identifies (type: "type of the mention; either user or team", \_id: "id of the user that is mentioned", username: "username of the user that is mentioned", name: name of the user that is mentioned). |
| groupable       | boolean                                  | Boolean that states whether or not this message should be grouped together with other messages from the same user                                                                                                                                    |
| channels        | Array of objects                         | An array of channel where message belongs to                                                                                                                                                                                                         |
| u               | Object                                   | The user who sent the message (either the \_id or username or name).                                                                                                                                                                                 |
| blocks          | MessageSurfaceLayout (enum)              | If a uikit message, then the uikit will block components.                                                                                                                                                                                            |
| alias           | string                                   | A way to display the message is "sent" from someone else other than the user who sent the message                                                                                                                                                    |
| md              | Root                                     | The message's content in a markdown format.                                                                                                                                                                                                          |
| \_hidden        | boolean                                  | Indicates whether the message is hidden.                                                                                                                                                                                                             |
| imported        | boolean                                  | Indicates whether the message is imported.                                                                                                                                                                                                           |
| replies         | Array of strings (user IDs)              | An array of user IDs representing the  message replies.                                                                                                                                                                                              |
| location        | Object                                   | The geographic location associated with the message.                                                                                                                                                                                                 |
| starred         | Array of objects                         | A list of users that have the message starred (list of user Ids (\_id)                                                                                                                                                                               |
| pinned          | boolean                                  | Indicates whether the message is pinned.                                                                                                                                                                                                             |
| pinnedAt        | Date                                     | The date and time when the message was pinned.                                                                                                                                                                                                       |
| pinnedBy        | Object                                   | Information about the user who pinned the message.                                                                                                                                                                                                   |
| unread          | boolean                                  | Indicates whether the message is unread.                                                                                                                                                                                                             |
| temp            | boolean                                  | Indicates whether the message is temporary.                                                                                                                                                                                                          |
| drid            | string                                   | The direct room id (if belongs to a direct room).                                                                                                                                                                                                    |
| tlm             | Date                                     | The date and time when the last thread message was sent.                                                                                                                                                                                             |
| dcount          | number                                   | The count of messages deleted in the thread.                                                                                                                                                                                                         |
| tcount          | number                                   | The count of messages in the thread.                                                                                                                                                                                                                 |
| t               | MessageTypesValues (enum)                | The type of the message.                                                                                                                                                                                                                             |
| e2e             | 'pending' or 'done' (enum)               | The end-to-end encryption status of the message.                                                                                                                                                                                                     |
| otrAck          | string                                   | The acknowledgement status of an off-the-record message.                                                                                                                                                                                             |
| urls            | Array of objects                         | An array of URLs contained within the message.                                                                                                                                                                                                       |
| actionLinks     | Array of objects (deprecated)            | An array of action links associated with the message.                                                                                                                                                                                                |
| file            | FileProp (deprecated)                    | The file property associated with the message.                                                                                                                                                                                                       |
| fileUpload      | Object                                   | Information about a file upload associated with the message.                                                                                                                                                                                         |
| files           | Array of FileProp objects                | An array of file properties associated with the message.                                                                                                                                                                                             |
| attachments     | Array of MessageAttachment objects       | An array of [attachment objects](../rest-api/endpoints/messaging/chat-endpoints/postmessage.md#attachments-detail), available only when the message has at least one attachment.                                                                     |
| reactions       | Object                                   | Object containing reaction information associated with the message.                                                                                                                                                                                  |
| private         | boolean                                  | Indicates whether the message is private.                                                                                                                                                                                                            |
| bot             | boolean (deprecated)                     | Indicates whether the message is sent by a bot.                                                                                                                                                                                                      |
| sentByEmail     | boolean                                  | Indicates whether the message was sent by email.                                                                                                                                                                                                     |
| webRtcCallEndTs | Date                                     | The date and time when a WebRTC call ended.                                                                                                                                                                                                          |
| role            | string                                   | The role associated with the message.                                                                                                                                                                                                                |
| avatar          | string                                   | A url to an image, that is accessible to anyone, to display as the avatar instead of the message user's account avatar                                                                                                                               |
| emoji           | string                                   | The emoji associated with the user who sent the message.                                                                                                                                                                                             |
| tokens          | Array of Token objects                   | An array of tokens extracted from the message content.                                                                                                                                                                                               |
| html            | string                                   | The HTML representation of the message.                                                                                                                                                                                                              |
| token           | string (deprecated)                      | A deprecated field used for messages sent by visitors.                                                                                                                                                                                               |
| federation      | Object                                   | Information about federation associated with the message.                                                                                                                                                                                            |
| slaData         | Object (used for specific message types) | Additional data related to SLA (Service Level Agreements) change history messages.                                                                                                                                                                   |
| priorityData    | Object (used for specific message types) | Additional data related to priority change history messages.                                                                                                                                                                                         |

{% hint style="info" %}
* The user presented on `u` and `editedBy` fields are a simplified version of the user information: (`_id`: The user id, `username`: The username, _name_: The name)
* The URL metadata contains several informational fields: (`url`: The URL itself (just as it appears on the message), `meta`: URL metadata (varies accord to the URL), `headers`: Some HTTP headers (varies accord to the URL), `parsedUrl`: The parsed URL broken into its parts)
{% endhint %}

### Message Type

Some of the message types are listed below. A full list of the message-type property can be found here

{% embed url="https://github.com/RocketChat/Rocket.Chat/blob/957c69d7ebdcf4dca02e7753bfd75086be11ca44/apps/meteor/app/lib/lib/MessageTypes.ts#L315" %}

| Type                   | Description              |
| ---------------------- | ------------------------ |
| `r`                    | Room name changed        |
| `au`                   | User added by            |
| `ru`                   | User removed by          |
| `ul`                   | User left                |
| `ult`                  | User left team           |
| `uj`                   | User joined channel      |
| `ujt`                  | User joined team         |
| `ut`                   | User joined conversation |
| `rm`                   | Message removed          |
| added-user-to-team     | Added user to team       |
| removed-user-from-team | Removed user from team   |
| user-muted             | User muted by            |

### Attachment Object

[The attachment object is fully described here](../rest-api/endpoints/messaging/chat-endpoints/postmessage.md#attachments-detail)

```javascript
{
    "messages": [
        {
            "_id": "message-id",
            "rid": "room-id",
            "msg": "Hello World!",
            "ts": { "$date": 1480377601 },
            "u": {
                "_id": "user-id",
                "username": "username"
            },
            "_updatedAt": { "$date": 1480377601 }
        },
        {
            "_id": "message-id",
            "rid": "room-id",
            "msg": "Hello!",
            "ts": { "$date": 1480377601 },
            "u": {
                "_id": "user-id",
                "username": "username"
            },
            "_updatedAt": { "$date":1480377601 },
            "editedAt": { "$date": 1480377601 },
            "editedBy": {
                "_id": "user-id",
                "username": "username"
            }
        }
    ]
}
```
