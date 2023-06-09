# Action Buttons

Action buttons are UI Kit elements that when registered, can be displayed and used in different contexts within the Rocket.Chat UI to trigger or initiate a set of action(s). The [Action button context](https://rocketchat.github.io/Rocket.Chat.Apps-engine/enums/ui\_uiactionbuttoncontext.uiactionbuttoncontext.html#message\_action) for example is `MESSAGE_ACTION`, `ROOM_ACTION`, `MESSAGE_BOX_ACTION` etc

To demonstrate this, we are going to create an action button on a message context that will simply display a text to let us know the interaction was received.

## Registering a button

Action buttons are registered during the `configurationExtend` lifecycle method. Here is an example:

```typescript
protected async extendConfiguration(configuration: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
    configuration.ui.registerButton({
        actionId: 'my-action-id', // this identifies your button in the interaction event
        labelI18n: 'my-action-name', // key of the i18n string containing the name of the button
        context: UIActionButtonContext.MESSAGE_ACTION, // in what context the action button will be displayed in the UI
    });
}
```

Registering a button requires `ui.registerButton` permission. Make sure to add it to your app manifest file (`app.json`); as shown below:

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

You can [deploy your app](../../getting-started/creating-an-app.md#testing-rocketchat-app) to test and see that the button gets added to the list of options against the context specified. In this case, a message.

Click on the options icon across any message and you will see the action we just created like seen below.

<figure><img src="../../../.gitbook/assets/UI Kit new Action Button" alt=""><figcaption><p>UI Kit new Action button</p></figcaption></figure>

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
                }).getBlocks(),
            });
        }

        return context.getInteractionResponder().successResponse();
    }

}
```
{% endcode %}

## Choosing when your button will be displayed

Most of the time you will have an action button that does something specific, and should not be displayed everywhere the context is available. For that, you can use the `when` prop when registering the button:

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

The button above can only be seen in public and private channels and direct messages, by users that have the `create-d` permission and have both the `admin` and `moderator` roles.

## Working with i18n

Localization for your App is very important to better suit different users.

To add localization to your App, create an `i18n` folder in the project's root directory and add `.json` files for the various languages.

In this case of this example, let us add an `en.json` file with the content

{% code title="en.json" %}
```json
{
    "my-action-name": "Test UI Action"
}
```
{% endcode %}

The above piece of code will simply create a reference for English against the \`labelI18n\` value we specified when registering the button.

{% hint style="success" %}
With these changes, deploy the app again and this time you will see something like the below when the button is clicked
{% endhint %}

<figure><img src="../../../.gitbook/assets/UI Kit Action Button triggered" alt=""><figcaption><p>UI Kit Action Button triggered</p></figcaption></figure>
