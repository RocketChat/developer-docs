# App Data Persistence

When you are developing apps, you can apply data persistence on object variables. By doing so, the variables are stored on the server and remain intact between sessions. You can save the data at the user level or the app level. For example, at the app level, if a comment text box is included in an app for users to provide feedback, the data entered in this box can be saved and remains persistent throughout the app for all users.

For Rocket.Chat apps, storing an app's state in the memory inside of an app is not recommended at all because Rocket.Chat servers can have several instances and each server has its own instance of an app. If the data is stored in the memory between different instances, it can lead to issues. To solve this problem, two approaches are suggested here:

* [**`IPersistence`**](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_IPersistence.IPersistence.html) **interface** (recommended): Apps-Engine provides the interface as an additional layer to store data as a compound key-value pair. An app only has access to its own persistent storage.
* **Custom fields**: This is a public way of storing data related to a message. You can attach some custom attributes (called `customFields`) to a message by creating or modifying the message. You should only use custom fields if you're okay with potentially having your data read and overwritten by someone else!

Let's look at further details of the **IPersistence** interface.

## `IPersistence` interface

The **Persistence** object uses **associations** to create records of compound key-value pairs. It's like an array of data that you are associating to a specific key.&#x20;

* The [`IPersistence`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_IPersistence.IPersistence.html) interface is used to create or update records in the persistence storage.&#x20;
* The [`IPersistenceRead`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_IPersistenceRead.IPersistenceRead.html) interface is used to read records.&#x20;
* You can create association records for data such as users, rooms, files, and so on. The available association models are defined in the [Enumeration `RocketChatAssociationModel` TypeScript Definition](https://rocketchat.github.io/Rocket.Chat.Apps-engine/enums/metadata\_RocketChatAssociations.RocketChatAssociationModel.html).

We can get `persistenceRead: IPersistenceRead` through the following way:

```typescript
// Get a persistence reader if you are using it in a method
// Here `this` means the main App class instance
const persistenceRead = this.getAccessors().reader.getPersistenceReader();

// Some methods provide a `read: IRead` parameter, so that you get a persistence
// reader through this parameter too.
const persistenceRead = read.getPersistenceRead();
```

For `persistence: IPersistence` writer object, you can only obtain it using parameters, which means you can not persist data within a method if the method doesn't have a `persistence: IPersistence` parameter  (typically it is an event handler that you are going to implement).

```typescript
function someMethod(context, read: IRead, persistence: IPersistence) {
    console.log(persistence); // The only way to fetch a persistence writer object
}
```

In the upcoming sections, we will look at two examples of implementing data persistence using the **Persistence** object — managing the internal state and storing user inputs.&#x20;
