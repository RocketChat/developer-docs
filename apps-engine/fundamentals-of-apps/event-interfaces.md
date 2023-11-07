# Event Interfaces and Handlers

An app can listen to certain events and react to them according to our requirements. You can implement an event interface if you want to listen to an event and handle its payload. The Rocket.Chat Apps-Engine provides various event interfaces. Typically, each interface contains one method that will be called before or after a Rocket.Chat event. Here we will learn some concepts about event interfaces and handlers in Rocket.Chat.

## Event interfaces

Event interfaces are the mechanism by which apps can connect themselves to the events on Rocket.Chat. For instance, when a message is sent, when a room or channel is created, or when a file is uploaded, the app can take some actions. For each of these events, there are respective interfaces that the app needs to use in order to properly connect to the events.

Let's consider an example, an app implements the post-room creation interface with the `PostRoomCreate` method. This tells Apps-Engine that the app wants to connect to that event. Whenever a room is created, Apps-Engine executes this method in the app.

You need to define the parameters for the method and the actions that you want the app to perform. Typically, there are two fundamental methods for each interface:

* A method to check: This signals the Apps-Engine whether the event handler should be executed.
* A method to execute the defined actions: This is the event handler.

{% hint style="info" %}
We are going to deprecate `check*` methods and won't add `check*` methods to event interfaces anymore. Please avoid using them as much as possible.
{% endhint %}

#### **Nomenclature**

* For interfaces: ‘**`I`**’ is prefixed to the event name.
* For the two interface methods:
  * **`‘check’`** is prefixed for the method that’s called for checking whether or not the event has occurred.
  * **`‘execute’`** is prefixed for the method that’s called for defining the actions that need to be performed by the app at the occurrence of the event.

For example, for the event `PreRoomCreatePrevent`, the corresponding nomenclature looks like this:

* **Interface**: `IPreRoomCreatePrevent`
* **Check method**: `checkPreRoomCreatePrevent`
* **Execute method**: `executePreRoomCreatePrevent`

This is the basic structure followed for most of the event interfaces supported by Rocket.Chat.&#x20;

## Event handlers

There are various ways to handle an event. When an event occurs, there are pre-handlers and post-handlers. The set of pre-handlers is executed before the event is completed. The set of post-handlers is executed when the event is completed. We recommend using pre-handlers to modify, extend, or change the data that is used for the event. If you want to listen for an event and not modify anything, use the post-handlers.

Here is an explanation of the handlers:

* **`Prevent`**: Determines whether the event should be prevented or not.
* **`Extend`**: Allows extending the data without being destructive of the data (adding an attachment to a message for example).
* **`Modify`**: Allows for destructive changes to the data (change any data).
* **`IPreEvent`**: Handlers that are called before an event happens.
* **`IPostEvent`**: Handlers that are called after an event happens.

In the main class of your app, the class name extends `App`. This tells the Apps-Engine that `App` is the main class. To use events, the app must implement the event interfaces and this is done by using the keyword implements and the name of the events, comma separated.

In the following sections, you will find the event interfaces supported by Rocket.Chat. The event interfaces are grouped based on the events such as — email, livechat, messages, rooms, users, and so on. You will also find [examples](../event-interfaces/examples.md) of how these interfaces can be implemented.
