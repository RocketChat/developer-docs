# Event Interfaces

The Rocket.Chat Apps Engine provides various event interfaces that you can implement for your app. Let’s learn some concepts in this document pertaining to event interfaces in Rocket.Chat.&#x20;

### Interfaces

One of the things an app can do is listen to certain events and react to them as per our requirements. Implement an event interface if you want to listen to this event and handle its payload data. Typically each interface contains one method that will be called before/after a Rocket.Chat event.

Event interfaces are the mechanism by which the apps can hook themselves into the events on Rocket.Chat. For instance, when a message is sent, an app can do something. Or when a room or channel or a discussion is created, the app can do something. When a file is uploaded, the app can do something. For each of these events, there are the respective interfaces that the app needs to use in order to properly hook into them.&#x20;

For example, if an app implements the post room creation interface with the `PostRoomCreate` method, it’s a way of telling the Apps Engine that the app wants to hook into that event, and whenever a room is created, Rocket.Chat is going to tell Apps Engine to execute this method inside this app. You need to define the parameters for the method and whatever actions you want the app to perform.&#x20;

Mostly, there will be 2 fundamental methods for each interface:&#x20;

* One for checking, which is used to signal Apps Engine whether the real event handler should actually be executed
* Other for executing the desired and defined actions, which is the real event handler

**Note:** We are going to deprecate `check*` methods and won't add `check*` methods to event interfaces anymore. Please avoid using them as much as possible.

In terms of the nomenclature, for interfaces, ‘**`I`**’ will be prefixed to the event. As for the 2 fundamental methods, ‘**`check`**’ will be prefixed for the method that’s called for checking whether or not the event has occurred; and ‘**`execute`**’ will be prefixed for the method that’s called for defining the actions that need to be performed by the app at the occurrence of the event.&#x20;

For example, `PreRoomCreatePrevent` is the event, this is how the corresponding nomenclature looks like:&#x20;

**Interface**: `IPreRoomCreatePrevent`

**Check method**: `checkPreRoomCreatePrevent`

**Execute method**: `executePreRoomCreatePrevent`

This is the basic structure followed for most of the event interfaces supported by Rocket.Chat.&#x20;

### Handlers

Handlers are essential "listeners" for different events, except there are various ways to handle an event. When something happens there are pre and post handlers. The set of pre handlers happens before the event is finalized. The set of post handlers happens after the event is finalized. With that said, the rule of thumb is: if you are going to modify, extend, or change the data backing the event then that should be done in the pre handlers. If you simply want to listen for when something happens and not modify anything, then the post is the way to go.

Here is an explanation of what each of them means:

* **`Prevent`**: This is run to determine whether the event should be prevented or not.
* **`Extend`**: This is run to allow extending the data without being destructive of the data (adding an attachment to a message for example).
* **`Modify`**: This is run and allows for destructive changes to the data (change any and everything).
* **`IPreEvent`** means handlers that are called before an event happens and **`IPostEvent`** means handlers that are called after an event happens.

In the main class, the class name extends App which tells Apps Engine that `App` is the main app class. To use the events, the app must implement the event interfaces and this is told to Apps Engine by the keyword ‘implements’ and the name of the events comma separated.&#x20;

Owing to the extensivity of the event interfaces supported by Rocket.Chat, we have grouped them based on the entities such as — email, livechat, messages, rooms, users, and so on, in the following sections.&#x20;

So once you zero in on the event, head to the corresponding section to know more about the entire list of interfaces supported for that particular event. For example, if it has anything to do with rooms such as creation of a room, or deletion of a room, refer to the documentation on Rooms under Event Interfaces.
