# Room

The room object represents any form of communication between two or more users.

There are at least two fields on the room object.

* `_id`: The room/user id (depends on the room type)
* `t`: The room type

The **IRoom** interface represents the **Room** object defining the properties and their types that can be associated with a Room. Room information is stored in the `rocketchat_room` collection on MongoDB.&#x20;

See the IRoom interface here.

{% embed url="https://github.com/RocketChat/Rocket.Chat/blob/develop/packages/core-typings/src/IRoom.ts" %}

## Room Object

<details>

<summary>Example Object</summary>

```json
{
  "_id": "DMDsF2QKqqQoXsxha",
  "fname": "private-channel",
  "customFields": {},
  "description": "",
  "broadcast": false,
  "encrypted": false,
  "federated": false,
  "name": "private-channel",
  "t": "p",
  "msgs": 6,
  "usersCount": 2,
  "u": {
    "_id": "rYhzFRd2QZjNwAAXX",
    "username": "rodriq"
  },
  "ts": {
    "$date": "2023-02-06T13:37:13.763Z"
  },
  "ro": false,
  "default": false,
  "sysMes": true,
  "_updatedAt": {
    "$date": "2023-03-08T21:17:55.262Z"
  },
  "lastMessage": {
    "_id": "5RPPKj9nyHEmbjqt8",
    "rid": "DMDsF2QKqqQoXsxha",
    "u": {
      "_id": "rYhzFRd2QZjNwAAXX",
      "username": "rodriq",
      "name": "Rodriq"
    },
    "msg": "Hey, check this file I've just shared: [temp Docs](https://docs.google.com/document/d/1oZG.../edit?usp=drivesdk)",
    "ts": {
      "$date": "2023-03-08T21:17:54.814Z"
    },
    "_updatedAt": {
      "$date": "2023-03-08T21:17:55.245Z"
    },
    "groupable": false,
    "attachments": [
      {
        "ts": "1970-01-01T00:00:00.000Z",
        "image_url": "data:image/png;base64,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"
      }
    ],
    "parseUrls": true,
    "urls": [
      {
        "url": "https://docs.google.com/document/d/1oZGW2...Bc/edit?usp=drivesdk"
      }
    ],
    "mentions": [],
    "channels": [],
    "md": [
      {
        "type": "PARAGRAPH",
        "value": [
          {
            "type": "PLAIN_TEXT",
            "value": "Hey, check this file I've just shared: "
          },
          {
            "type": "LINK",
            "value": {
              "src": {
                "type": "PLAIN_TEXT",
                "value": "https://docs.google.com/document/d/1oZGW2bd...LBc/edit?usp=drivesdk"
              },
              "label": [
                {
                  "type": "PLAIN_TEXT",
                  "value": "temp Microservices Docs"
                }
              ]
            }
          }
        ]
      }
    ]
  },
  "lm": {
    "$date": "2023-03-08T21:17:54.814Z"
  }
}
```

</details>

### Fields

The Room object has these fields

| Field                 | Data Type                        | Description                                                                                                                                         |
| --------------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| \_id                  | string                           | Room ID                                                                                                                                             |
| t                     | string                           | Room type. E.g c = chanel, d = direct message, l = live chat, p=private chat                                                                        |
| name                  | string                           | The name of the room                                                                                                                                |
| fname                 | string                           | The full name of the room                                                                                                                           |
| msgs                  | number                           | The number of messages in the room                                                                                                                  |
| default               | true                             | Indicates if the room is the default room                                                                                                           |
| broadcast             | true                             | Indicates if the room is a broadcast room                                                                                                           |
| featured              | true                             | Indicates if the room is featured                                                                                                                   |
| announcement          | string                           | The announcement or summary of the room                                                                                                             |
| joinCodeRequired      | boolean                          | Indicates if a join code is required to enter the room                                                                                              |
| announcementDetails   | { style?: string }               | Additional details about the room announcement, such as the style                                                                                   |
| encrypted             | boolean                          | Indicates if the room is encrypted                                                                                                                  |
| topic                 | string                           | The topic of the room                                                                                                                               |
| reactWhenReadOnly     | boolean                          | Indicates if reactions are allowed when the room is read-only                                                                                       |
| sysMes                | MessageTypesValues\[] \| boolean | Indicates whether system messages are enabled or an array of allowed system message types                                                           |
| u                     | string                           | Information about the user who created the room(\_id: string, username: string, name: string )                                                      |
| uids                  | Array\<string>                   | Array of user IDs in the room                                                                                                                       |
| lastMessage           | IMessage                         | The last message sent in the room                                                                                                                   |
| lm                    | Date                             | Timestamp of the last message                                                                                                                       |
| usersCount            | number                           | The number of users in the room                                                                                                                     |
| callStatus            | CallStatus                       | The status of a call in the room                                                                                                                    |
| webRtcCallStartTime   | Date                             | The start time of a WebRTC call in the room                                                                                                         |
| servedBy              | string                           | Information about the user who served the room{ \_id: string }                                                                                      |
| streamingOptions      | string                           | Options for streaming content in the room { id?: string, type?: string, url?: string, thumbnail?: string, isAudioOnly?: boolean, message?: string } |
| prid                  | string                           | The primary room ID (for threads)                                                                                                                   |
| avatarETag            | string                           | The ETag for the room avatar                                                                                                                        |
| teamMain              | boolean                          | Indicates if the room is the main room for a team                                                                                                   |
| teamId                | string                           | The ID of the team the room belongs to                                                                                                              |
| teamDefault           | boolean                          | Indicates if the room is the default room for the team                                                                                              |
| open                  | boolean                          | Indicates if the room is open                                                                                                                       |
| autoTranslateLanguage | string                           | The language used for automatic translation in the room                                                                                             |
| autoTranslate         | boolean                          | Indicates if automatic translation is enabled for the room                                                                                          |
| unread                | number                           | The number of unread messages in the room                                                                                                           |
| alert                 | boolean                          | Indicates if there is an alert in the room                                                                                                          |
| hideUnreadStatus      | boolean                          | Indicates if the unread status is hidden                                                                                                            |
| hideMentionStatus     | boolean                          | Indicates if the mention status is hidden                                                                                                           |
| muted                 | string\[]                        | Array of user IDs who are muted in the room                                                                                                         |
| unmuted               | string\[]                        | Array of user IDs who are not muted in the room                                                                                                     |
| usernames             | string\[]                        | Array of usernames in the room                                                                                                                      |
| ts                    | Date                             | Timestamp of when the room was created                                                                                                              |
| cl                    | boolean                          | Indicates if the room is a channel                                                                                                                  |
| ro                    | boolean                          | Indicates if the room is read-only                                                                                                                  |
| favorite              | boolean                          | Indicates if the room is marked as a favorite                                                                                                       |
| archived              | boolean                          | Indicates if the room is archived                                                                                                                   |
| description           | string                           | Description or summary of the room                                                                                                                  |
| createdOTR            | boolean                          | Indicates if the room was created as an OTR (off-the-record) room                                                                                   |
| e2eKeyId              | string                           | Key ID for end-to-end encryption in the room                                                                                                        |
| federated             | boolean                          | (Deprecated) Indicates if the room is federated                                                                                                     |
| customFields          | Object                           | (Deprecated) Custom fields for additional room information                                                                                          |
| channel               | { \_id: string }                 | Information about the channel the room belongs to                                                                                                   |

### Room Types

* `d`: Direct messages
* `c`: Public channel
* `p`: Private channel
* `discussions`: Team or channel discussions
* `teams`: Workspace teams
* `l`: Livechat
* `v`: Omnichannel VoIP rooms

The information that comes with the room object changes according to its type.

{% tabs %}
{% tab title="Direct chat" %}
A direct chat between two users. In this case, the room object only has two fields:

* `_id`: The room id
* `t`: The room type (in this case `d`)

Example:

```javascript
{
    "_id": "room-id",
    "t": "d"
}
```

You'll need to access the room information using data from [Get Subscriptions](https://docs.rocket.chat/developer-guides/realtime-api/method-calls/get-subscriptions).
{% endtab %}

{% tab title="Chat" %}
An open chatroom. A chat contains more information about the room as it follows:

* `_id`: The room id
* `t`: The room type (in this case `c`)
* `name`: The room name
* `u`: The room creator (it may return a null user)
* `topic`: (Optional) The room topic
* `muted`: (Optional) A collection of muted users by its username
* `jitsiTimeout`: (Optional) (?)

Example:

```javascript
{
    "_id": "room-id",
    "t": "c",
    "name": "room-name",
    "u": { "_id": "user-id", "username": "username" },
    "topic": "room-topic",
    "muted": [ "username" ],
    "jitsiTimeout": { "$date": 1480377601 }
}
```
{% endtab %}

{% tab title="Private chat" %}
A private chatroom. This type of room resembles the open chat room with an addition.

* `_id`: The room id
* `t`: The room type (in this case `p`)
* `name`: The room name
* `u`: The room creator (it may return a null user)
* `topic`: (Optional) The room topic
* `muted`: (Optional) A collection of muted users by its username
* `jitsiTimeout`: (Optional) (?)
* `ro`: Flags if the room is read-only

Example:

```javascript
{
    "_id": "room-id",
    "t": "p",
    "name": "room-name",
    "u": { "_id": null, "username": null },
    "topic": "room-topic",
    "ro": false // This room is not read-only
}
```
{% endtab %}
{% endtabs %}

###

