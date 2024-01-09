# Storing User Input Example

In this example, we will show how to manage persistence methods with a class.&#x20;

Consider that you are going to persist some messages. Create a class called `MessagePersistence`. Then you can add a series of static methods as shown below to add, remove, and query data from the database.

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```typescript
import { IPersistence, IPersistenceRead } from '@rocket.chat/apps-engine/definition/accessors';
import { RocketChatAssociationModel, RocketChatAssociationRecord } from '@rocket.chat/apps-engine/definition/metadata';
import { IRoom } from '@rocket.chat/apps-engine/definition/rooms';

export class MessagePersistence {
    // add records
    public static async persist(persis: IPersistence, room: IRoom, id: string): Promise<boolean> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'), 
            new RocketChatAssociationRecord(RocketChatAssociationModel.ROOM, room.id),
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, id),
        ];

        try {
            await persis.updateByAssociations(associations, { id }, true);
        } catch (err) {
            console.warn(err);
            return false;
        }

        return true;
    }

    // query all records within the "scope" - message
    public static async findAll(persis: IPersistenceRead): Promise<Array<string>> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'),
        ];

        let result: Array<string> = [];
        try {
            const records: Array<{ id: string }> = (await persis.readByAssociations(associations)) as Array<{ id: string }>;

            if (records.length) {
                result = records.map(({ id }) => id);
            }
        } catch (err) {
            console.warn(err);
        }

        return result;
    }

    // query all records by room within the "scope" - message
    public static async findByRoom(persis: IPersistenceRead, room: IRoom): Promise<Array<string>> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'),
            new RocketChatAssociationRecord(RocketChatAssociationModel.ROOM, room.id),
        ];

        let result: Array<string> = [];
        try {
            const records: Array<{ id: string }> = (await persis.readByAssociations(associations)) as Array<{ id: string }>;

            if (records.length) {
                result = records.map(({ id }) => id);
            }
        } catch (err) {
            console.warn(err);
        }

        return result;
    }

    // remove all records by room within the "scope" - message
    public static async removeByRoom(persis: IPersistence, room: IRoom): Promise<boolean> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'),
            new RocketChatAssociationRecord(RocketChatAssociationModel.ROOM, room.id),
        ];

        try {
            await persis.removeByAssociations(associations);
        } catch (err) {
            console.warn(err);
            return false;
        }

        return true;
    }

    // remove all records by id within the "scope" - message
    public static async removeById(persis: IPersistence, id: string): Promise<boolean> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'),
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, id),
        ];

        try {
            await persis.removeByAssociations(associations);
        } catch (err) {
            console.warn(err);
            return false;
        }

        return true;
    }

    // remove all records within the "scope" - message
    public static async clear(persis): Promise<boolean> {
        const associations: Array<RocketChatAssociationRecord> = [
            new RocketChatAssociationRecord(RocketChatAssociationModel.MISC, 'message'),
        ];

        try {
            await persis.removeByAssociations(associations);
        } catch (err) {
            console.warn(err);
            return false;
        }

        return true;
    }
}
```
{% endcode %}
