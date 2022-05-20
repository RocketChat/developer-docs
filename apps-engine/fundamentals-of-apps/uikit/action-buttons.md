# Action Buttons

It is now possible for a Rocket.Chat App to register action buttons to be displayed in different contexts in Rocket.Chat UI, such as message actions, room actions, and message box actions.

## Registering a button

Action buttons can be registered during the `configurationExtend` lifecycle method. Here is an example:

```typescript
protected async extendConfiguration(configuration: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
    configuration.ui.registerButton({
        actionId: 'my-action-id', // this identifies your button in the interaction event
        labelI18n: 'my-action-name', // key of the i18n string containing the name of the button
        context: UIActionButtonContext.MESSAGE_ACTION, // in what context the action button will be displayed in the UI
    });
}
```

Registering a button requires the `ui.registerButton` permission. Make sure to add it to your app manifest file (`app.json`). It will look similar to the following:

{% code title="app.json" %}
```json
{
    "id": "some-app-id",
    "name": "My App",
    // ... other definitions
    "permissions": [
        { "name": "ui.registerButtons" }
    ]
}
```
{% endcode %}

That button will be shown as follows:

![](<../../../.gitbook/assets/image (100).png>)

## Handling an interaction

Whenever the user clicks one of the action buttons, the app receives an interaction event. Here is an example of how to handle it:

{% code title="MyApp.ts" %}
```typescript
export class MyApp extends App implements IUIKitInteractionHandler {
    public async executeActionButtonHandler(
        context: UIKitActionButtonInteractionContext,
        read: IRead,
        http: IHttp,
        persistence: IPersistence,
        modify: IModify
    ): Promise<IUIKitResponse> {
        const { 
            buttonContext, 
            actionId, 
            triggerId, 
            user, 
            room, 
            message,
        } = context.getInteractionData();

        // If you have multiple action buttons, use `actionId` to determine 
        // which one the user interacted with
        if (actionId === 'my-action-id') {
            const blockBuilder = modify.getCreator().getBlockBuilder();
            
            return context.getInteractionResponder().openModalViewResponse({
                title: blockBuilder.newPlainTextObject('Interaction received'),
                blocks: blockBuilder.addSectionBlock({
                    text: blockBuilder.newPlainTextObject('We received your interaction, thanks!')
                }),
            });
        }

        return context.getInteractionResponder().successResponse();
    }

}
```
{% endcode %}

## Choosing when your button will be displayed

Most of the times you will have an action button that does something specific, and should not be displayed everywhere the context is available. For that, you can use the `when` prop when registering the button:

```typescript
protected async extendConfiguration(configuration: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
    configuration.ui.registerButton({
        actionId: 'my-action-id',
        labelI18n: 'my-action-name',
        context: UIActionButtonContext.MESSAGE_ACTION,
        // If you want to choose `when` the button should be displayed
        when: {
            roomTypes: [
                RoomTypeFilter.PUBLIC_CHANNEL, 
                RoomTypeFilter.PRIVATE_CHANNEL, 
                RoomTypeFilter.DIRECT,
            ],
            hasOnePermission: ['create-d'],
            hasAllRoles: ['admin', 'moderator'],
        }
    });
}
```

The button above would only be seen in public and private channels and direct messages, by users that have the `create-d` permission and have both the `admin` and `moderator` roles.
