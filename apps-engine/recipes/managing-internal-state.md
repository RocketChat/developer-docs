# Managing Internal State

It's a common need to manage the internal state of your app. **Storing an app's state in the memory inside of an app is not recommended at all** because a Rocket.Chat server can have several instances and each server has its own instance of an app. If the data is stored in the memory between different instances, it can lead to issues. To solve this problem, two approaches are suggested here.

### Persistence APIs (Recommended)

The [IPersistence](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_ipersistence.ipersistence.html) interface is provided to create or update records in the persistence storage. The [IPersistenceRead](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_ipersistenceread.ipersistenceread.html) interface is provided to read records. In the example below, you can see how to manage your app's internal state using persistence APIs.

Assuming that we're creating an app that records how many messages are sent on the server, we can write a `PostMessageSent` event handler as shown below:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```typescript
public async executePostMessageSent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void> {
    const association = new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message-count');
    const persis = read.getPersistenceReader();
    
    try {
        let count = 0;
        const record = await persis.readByAssociation(association);
        if (record?.count) count = record.count;

        await persistence.createWithAssociation({ count: ++count || 0 }, association);

        console.log(`Message Sent Count: ${ count }`)
    } catch (err) {
        return this.getLogger().error(err);
    }
}
```
{% endcode %}

Here, the internal state is `count` but not the count variable whose data is stored in the memory. We use the temporary variable `count` to store the number of messages sent and retrieving from the persistence. Every time the handler `executePostMessageSent` is called, we increase the count by one and then store it back to the persistence storage.

In this way, even in a cluster environment, your app inside each Rocket.Chat instance can share data from a single data source, the Rocket.Chat persistence storage and maintain data consistency.

[Check the full demo here for more details!](https://github.com/RocketChat/Apps.RocketChat.Tester/tree/recipes/managing-internal-state)

### Message `customFields`

Besides Persistence APIs, `customFields` is a public way of storing data related to a message. You can attach some custom attributes (called `customFields`) to a message by creating or modifying the message. You should only use `customFields` if you're okay with potentially having them read and overwritten by someone else!
