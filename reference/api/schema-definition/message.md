# Message

The message object is the very soul of a conversation. It encapsulates all the information need in order to represent a single entry on a message list.

### Message Type

Some of the message types are listed below. A full list of the message type property can be found here

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

### Message Object

The message object contains these fields.

| Field Name                  | Description                                                                                                                                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `_id`                       | The unique id for the message.                                                                                                                                                                         |
| `rid`                       | The unique id for the room. This will identify the room that the message belongs to. Example: '`GENERAL`'                                                                                              |
| `msg`                       | The textual message                                                                                                                                                                                    |
| `tmid`                      | The unique identifier for the message thread. Example: '`7aDSXtjMA3KPLxLjt`'                                                                                                                           |
| `ts`                        | A timestamp of when the message was created. (The date of creation on client). Example: '2019-04-08T13:15:52.017Z'                                                                                     |
| `mentions`                  | Identifies (type: "type of the mention; either user or team", \_id: "id of the user that is mentioned", username: "username of the user that is mentioned", name: name of the user that is mentioned). |
| `u`                         | The user who sent the message (either the \_id or username or name).                                                                                                                                   |
| `blocks`                    | If a uikit message, then the uikit will block components.                                                                                                                                              |
| `md`                        | A markdown object                                                                                                                                                                                      |
| `starred`                   | A list of users that have the message starred (list of user Ids (\_id)                                                                                                                                 |
| `pinned`                    | Identifies if the message is pinned or not.                                                                                                                                                            |
| `unread`                    | Identifies if the message unread or not.                                                                                                                                                               |
| `temp`                      | Identifies if the message is temporal                                                                                                                                                                  |
| `drid`                      | The direct room id (if belongs to a direct room).                                                                                                                                                      |
| `_updatedAt`                | A timestamp of when the message got saved on the server.                                                                                                                                               |
| `editedAt`_(Optional)_.     | A timestamp of when the message was edited                                                                                                                                                             |
| `editedBy` _(Optional)_     | The user who edited the message.                                                                                                                                                                       |
| `urls (`_Optional_`)`       | A collection of URLs metadata. Available when the message contains at least one URL.                                                                                                                   |
| `attachments(`_Optional_`)` | A collection of [attachment objects](../rest-api/endpoints/core-endpoints/chat-endpoints/postmessage.md#attachments-detail), available only when the message has at least one attachment.              |
| `alias(`_Optional_`)`       | A way to display the message is "sent" from someone else other than the user who sent the message                                                                                                      |
| `avatar(Optional)`          | A url to an image, that is accessible to anyone, to display as the avatar instead of the message user's account avatar                                                                                 |
| `groupable(Optional)`       | Boolean that states whether or not this message should be grouped together with other messages from the same user                                                                                      |
| `channel(Optional)`         | The channel where message belongs to                                                                                                                                                                   |
| `parseUrls(Optional)`       | Identifies whether Rocket.Chat should try and parse the urls or not                                                                                                                                    |
| `tlm(Optional)`             | The thread last message, is used to inform the last time some message was sent inside the thread.                                                                                                      |
| `reactions`                 | Reactions on the message                                                                                                                                                                               |

The user presented on `u` and `editedBy` fields are a simplified version of the user information:

* `_id`: The user id
* `username`: The username
* name: The name

```
// "u": {
                "_id": "p4a8YxvLQEHmiBKTS",
                "username": "marcos.defendi",
                "name": "Marcos Defendi"
            },
```

The URL metadata contains several informational fields:

* `url`: The URL itself (just as it appears on the message)
* `meta`: URL metadata (varies accord to the URL)
* `headers`: Some HTTP headers (varies accord to the URL)
* `parsedUrl`: The parsed URL broken into its parts

[The attachment object is fully described here](../rest-api/endpoints/core-endpoints/chat-endpoints/postmessage.md#attachments-detail)

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
