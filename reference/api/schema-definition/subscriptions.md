# Subscriptions

The subscription object contains the information about the room and the user relation to it. You can check the `ISubscription` interface here [https://github.com/RocketChat/Rocket.Chat/blob/develop/definition/ISubscription.ts](https://github.com/RocketChat/Rocket.Chat/blob/develop/definition/ISubscription.ts)

* `t`: The room type \(the same used on the \[room object\]\[1\]\)
* `ts`: Timestamp the room was created at, so this should equal the room's `ts` field
* `ls`: Last seen timestamp \(The last time the user has seen a message in the room\)
* `name`: The room name
* `rid`: The room id
* `u`: An simple `user` object with its id and username
* `open`: Whether the room the subscription is for has been opened or not \(defaults to false on direct messages\). This is used in the clients to determine whether the user can see this subscription in their list, since you can hide rooms from being visible without leaving them.
* `alert`: Whether there is an alert to be displayed to the user
* `roles`: \(Optional\) The collection of roles the user belongs to \(at least one `role-name` will be present\)
* `unread`: The total of unread messages
* `tunread`: \(Optional\) List of ids of unread threads
* `tunreadGroup`: \(Optional\)List of thread ids that contain an unread mention to a group which the user is part of
* `tunreadUser`: \(Optional\) List of thread ids that contain an unread mention to the user
* `_updatedAt`: Timestamp of when the subscription record was updated
* `_id`: The subscription id
* `lr`: Timestamp of the last reply in a thread
* `hideUnreadStatus`: Whether the subscribed room should be marked as containing unread messages in the UI or not
* `teamMain`: Whether this subscription points to the main room of a team or not
* `teamId`:  \(Optional\) If the subscription points to a team room, the team's id should be present in this field
* `userMentions`: Number of unread mentions to the user in the room
* `groupMentions`: Number of unread mentions to a group which the user is part of \(e.g @all, @here\)
* `prid`: Parent room id. This will only be available if this is a subscription to a discussion
* `onHold`: \(Omnichannel\) Whether or not this room has been put on hold

An example:

```javascript
{
    "t": "d",
    "ts": { "$date": 1480377601 },
    "ls": { "$date": 1480377601 },
    "name": "roomName",
    "rid": "room-id",
    "u": { "_id": "user-id", "username": "username" },
    "open": true,
    "alert": false,
    "unread": 0,
    "tunread": 1,
    "tunreadGroup": 1,
    "tunreadUser": 1,
    "_updatedAt": { "$date": 1480377601 },
    "_id": "subscription-id",
    "lr": { "$date": 1480377601 },
    "hideUnreadStatus": false,
    "teamMain": true,
    "teamId": "team-id",
    "userMentions": 1,
    "groupMentions": 1,
    "onHold": false
}
```

