---
description: 'How to manage your app''s internal state, here is the recipe!'
---

# Managing Internal State

It's a common need to manage internal state in your app.  **Storing app's state in the memory inside of an app is not recommended at all** because a Rocket.Chat server can have several instances and each server has its own instance of an app. If the data, such as confirmation for context, stored in the memory between the different instances then the problem occrurs.  There're 2 approaches here suggested to be applied to solve the problem above.

### Persistence APIs \(Recommended\)

There's [IPersistence](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors_ipersistence.ipersistence.html) interface provided for creating/updating records in the persistence storage and [IPersistenceRead](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors_ipersistenceread.ipersistenceread.html) interface provided for reading records.

Assuming that we're creating an app that records how many messages on the server sent, we can write a post message sent event handler like bellow:

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

Here we use temporary variable count for storing the number of messages sent retrieving from the persistence. Every time the handler executePostMessageSent called, we increase the count by 1 and then store it back to the persistence storage. 

In this way, even in a cluster environment, your app inside each Rocket.Chat instance can share data from a single data source - Rocket.Chat persistence storage and maintain the data consistency.

[Check the full demo here for more details!](https://github.com/RocketChat/Apps.RocketChat.Tester/tree/recipes/managing-internal-state)

### Message customFields

Besides Persistence APIs,  `customFields`  is a public way of stroing data related to a message. You can attach some custom "attributes" \(called customFields\) to a message by creating/modifying the message. You should only use the `customFields` if you're ok with potentially having them read and overwritten by someone else!

