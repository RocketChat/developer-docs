# Action Buttons

In the previous sections, we have learned about creating contextual bars and the list of building blocks available in the UIKit. Let's expand on this and see how to create interactive buttons and handle the interactions.

Action buttons are UIKit elements that when registered, can be displayed and used in different contexts within the Rocket.Chat UI to trigger or initiate a set of actions. The [Action button context](https://rocketchat.github.io/Rocket.Chat.Apps-engine/enums/ui\_uiactionbuttoncontext.uiactionbuttoncontext.html#message\_action) for example is `MESSAGE_ACTION`, `ROOM_ACTION`, `MESSAGE_BOX_ACTION`, etc.

To demonstrate this, we are going to create an action button on a message context that will simply display a text to let us know that the interaction was received.

## Register a button

Action buttons are registered during the `extendConfiguration` lifecycle method. The code snippet is as follows:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```typescript
protected async extendConfiguration(configuration: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
    configuration.ui.registerButton({
        actionId: 'my-action-id', // this identifies your button in the interaction event
        labelI18n: 'my-action-name', // key of the i18n string containing the name of the button
        context: UIActionButtonContext.MESSAGE_ACTION, // the context in which the action button will be displayed on the UI
    });
}
```
{% endcode %}

Registering a button requires `ui.registerButton` permission. Add it to your app manifest file (`app.json`) as shown below:

{% code title="app.json" %}
```json
{
    "id": "some-app-id",
    "name": "App Name",
    // ... other definitions
    "permissions": [
        { "name": "ui.registerButtons" }
    ]
}
```
{% endcode %}

{% hint style="info" %}
For more information, see [Permission System](../../permission-system.md).
{% endhint %}

You can deploy your app to test and see that the button gets added to the list of options against the context specified, in this case, a message.

Click on the options icon across any message and you will see the action we just created as seen below:

<figure><img src="../../../.gitbook/assets/UI Kit new Action Button" alt=""><figcaption><p>UI Kit new Action button</p></figcaption></figure>

## Handle an interaction

After registering the button, we can see the button but cannot take any actions with it. Now whenever the user clicks on the action button, we want the app to receive an interaction event.

Here is an example of how to handle it:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
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

Now deploy and test the app again. You will see that when you click the action button that we had registered, a modal named `Interaction received` opens with the message `We received your interaction, thanks!`. You can also view the `Logs` section of your app for details.

## Choose when your button is displayed

Most of the time you will have an action button that does something specific and should not be displayed everywhere the context is available. For that, you can use the `when` prop while registering the button as follows:

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```typescript
protected async extendConfiguration(configuration: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
    await configuration.ui.registerButton({
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
{% endcode %}

Now the button can only be seen in public and private channels and direct messages, by users that have the `create-d` permission and have both the `admin` and `moderator` roles.

## Add localization

Localization for your app is important to better suit different users. To add localization to your app, create an `i18n` folder in the project's root directory and add `.json` files for the various languages.

For this example, let us add an `en.json` file with the content as follows:

{% code title="en.json" %}
```json
{
    "my-action-name": "Test UI Action"
}
```
{% endcode %}

This code will simply create a reference for the English language against the `labelI18n` value we specified when registering the button.

With these changes, deploy the app again and this time you will see something like the screenshot below when the button is clicked.

<figure><img src="../../../.gitbook/assets/UI Kit Action Button triggered" alt=""><figcaption><p>UI Kit Action Button triggered</p></figcaption></figure>

With this example, we know how to handle interactions using action buttons and specify when the button should be displayed. We've also taken a look at defining localization files here.&#x20;

To create such interfaces with Apps-Engine for the Rocket.Chat UI, you need to follow some guidelines. In the next topic, you will find detailed guidelines for menus, messages, chatbots, and so on.
