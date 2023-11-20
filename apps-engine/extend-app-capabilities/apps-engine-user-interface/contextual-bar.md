# Contextual Bar

On this page, we will see how to use the UIKit components to create a contextual bar.

A contextual bar is a sidebar displayed on the screen. You need to pass a `BlockBuilder` object containing the content you want to display and call the following methods:

```typescript
// to create a new contextual bar
await modify.getUiController().openContextualBarView(blocks, { triggerId }, user);

// to update an existing contextual bar
await modify.getUiController().updateContextualBarView(blocks, { triggerId }, user);
```

Let's look at a sample app to open the contextual bar. This app consists of two main parts:

* A slash command from where we can get a valid `triggerId.`&#x20;
* The function that opens the contextual bar using the`triggerId`.

{% hint style="info" %}
You can clone the app and test it in your own Rocker.Chat server:\
[https://github.com/RocketChat/apps-contextual-bar-open-example](https://github.com/RocketChat/apps-contextual-bar-open-example)
{% endhint %}

1. We are importing the following files:

{% code overflow="wrap" fullWidth="false" %}
```typescript
import {
    IAppAccessors,
    IConfigurationExtend,
    IHttp,
    ILogger,
    IModify,
    IPersistence,
    IRead,
} from '@rocket.chat/apps-engine/definition/accessors';

import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';
import { ISlashCommand, SlashCommandContext } from '@rocket.chat/apps-engine/definition/slashcommands';

import { BlockElementType, ISectionBlock, IUIKitResponse, UIKitBlockInteractionContext, UIKitViewSubmitInteractionContext } from '@rocket.chat/apps-engine/definition/uikit';

import { IUIKitContextualBarViewParam } from '@rocket.chat/apps-engine/definition/uikit/UIKitInteractionResponder';
```
{% endcode %}

2. Now we will add a class `OpenCtxBarCommand` that implements `ISlashCommand`. In this class, we are doing the following:&#x20;
   1. Define the slash command to get the trigger ID. Without the trigger ID, it is not possible to open the contextual bar.
   2. Call the function to create the blocks that we will render inside the contextual bar.
   3. Call the method that opens the contextual bar.

{% code overflow="wrap" %}
```typescript
class OpenCtxBarCommand implements ISlashCommand {
    // this is what we will type when calling the slashcommand: /contextualbar
    public command = 'contextualbar';
    public i18nParamsExample = 'slashcommand_params';
    public i18nDescription = 'slashcommand_description';
    public providesPreview = false;

    constructor(private readonly app: App) {}

    public async executor(context: SlashCommandContext, _read: IRead, modify: IModify): Promise<void> {
        const triggerId = context.getTriggerId() as string; // [1]
        const user = context.getSender();

        const contextualbarBlocks = createContextualBarBlocks(modify); // [2]

        await modify.getUiController().openContextualBarView(contextualbarBlocks, {                 triggerId }, user); // [3]
    }
}

// [1] - first we get the triggerId  to open the surface (without this it would not be possible to open the contextual bar)
// [2] - then we create the blocks we will render inside the contextual bar.
// [3] - then call the method that opens the contextual bar.
```
{% endcode %}

3. After creating the class, we will define a method called `createContextualBarBlocks` to implement the following:
   1. Create the blocks that will be rendered inside the contextual bar.
   2. Add a section block that consists of a message that shows the current date-time and a button that refreshes the date-time shown in the message.
   3. Return the contextual bar structure containing its title and a submit button.

{% code overflow="wrap" %}
```typescript
function createContextualBarBlocks(modify: IModify, viewId?: string): IUIKitContextualBarViewParam {
    const blocks = modify.getCreator().getBlockBuilder();

    const date = new Date().toISOString();

    blocks.addSectionBlock({
        text: blocks.newMarkdownTextObject(`The current date-time is\n${date}`), // [4]
        accessory: { // [5]
            type: BlockElementType.BUTTON,
            actionId: 'date',
            text: blocks.newPlainTextObject('Refresh'),
            value: date,
        },
    });

    return { // [6]
        id: viewId || 'contextualbarId',
        title: blocks.newPlainTextObject('Contextual Bar'),
        submit: blocks.newButtonElement({
            text: blocks.newPlainTextObject('Submit'),
        }),
        blocks: blocks.getBlocks(),
    };
}
// This method creates the blocks that will be rendered inside the contextual bar.
// It consists of:
// [4] - a message that presents the current date-time.
// [5] - a button that updates the date-time shown in the message.
// [6] - the contextual bar structure containing its title and a submit button.
```
{% endcode %}

4. Finally, we will modify the main app class as follows:
   1. Provide the slash command that we will use.
   2. Listen for the date-time button to be clicked.
   3. Update the contextual bar's content.
   4. Listen for the user to click the `Submit` button.
   5. Get the date-time data from the contextual bar.
   6. Log the data to the console.

{% code overflow="wrap" %}
```typescript
export class CtxbarExampleApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    // [7]
    protected async extendConfiguration(configuration: IConfigurationExtend): Promise<void> {
        await configuration.slashCommands.provideSlashCommand(
            new OpenCtxBarCommand(this),
        )
    }

    // [8]
    public async executeBlockActionHandler(context: UIKitBlockInteractionContext, _read: IRead, _http: IHttp, _persistence: IPersistence, modify: IModify) {
        const data = context.getInteractionData();

        const contextualbarBlocks = createContextualBarBlocks(modify, data.container.id);

        // [9]
        await modify.getUiController().updateContextualBarView(contextualbarBlocks, { triggerId: data.triggerId }, data.user);

        return {
            success: true,
        };
    }

    // [10]
    public async executeViewSubmitHandler(context: UIKitViewSubmitInteractionContext): Promise<IUIKitResponse> {
        const data = context.getInteractionData()

        // [11]
        const text = (data.view.blocks[0] as ISectionBlock).text.text;

        // [12]
        console.log(text);

        return {
            success: true,
        };
    }
}

// Here in the main class, we setup the whole app:
// [7] first we provide the slash command we will use.
// [8] then we listen to when the button on [5] is pressed.
// [9] we update the contextual bar's content.
// [10] listen for when the user presses the 'submit' button.
// [11] get the content (date-time) from the contextual bar.
// [12] logs the data to the console.
```
{% endcode %}

5. Deploy and test this app by sending `"/contextualbar <text>"` to any channel. As soon as you send this message, the contextual bar opens on the right-side of the UI. The contextual bar displays the current date-time, the refresh button, and the submit button.&#x20;
6. Click **Refresh** to update the current date-time. Clicking **Submit** logs the date-time to the app logs and closes the contextual bar.
7. Go to the **Logs** section of your app to view the details.

Great work! With this example, you have learned to create user interactions for your apps! While we have only used a contextual bar and buttons here, you can learn about all the building blocks that are available in the UIKit in the next section.
