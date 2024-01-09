# Managing Internal State Example

In this example, we are creating an app that records the number of messages sent on the server using the **Persistence** object.&#x20;

To store the message count, we can write an `executePostMessageSent` event handler as shown below:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```typescript
public async executePostMessageSent(message: IMessage, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void> {
//create a new association to count messages
    const association = new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message-count');
    const persis = read.getPersistenceReader();
    
    try {
        let count = 0;
        const record = await persis.readByAssociation(association);
        if (record?.count) count = record.count;

        await persistence.createWithAssociation({ count: ++count || 0 }, association);
//log the number of messages
        console.log(`Message Sent Count: ${ count }`)
    } catch (err) {
        return this.getLogger().error(err);
    }
}
```
{% endcode %}

Here,&#x20;

* The internal state is `count` but not the count variable whose data is stored in the memory. We use the temporary variable `count` to store the number of messages sent and retrieve this number from the persistence storage.&#x20;
* Every time the handler `executePostMessageSent` is called, we increase the count by one and then store it back to the persistence storage.

In this way, even in a cluster environment, your app in each Rocket.Chat instance can share data from a single data source, the Rocket.Chat persistence storage and maintain data consistency.

[Check the full demo here for more details!](https://github.com/RocketChat/Apps.RocketChat.Tester/tree/recipes/managing-internal-state)
