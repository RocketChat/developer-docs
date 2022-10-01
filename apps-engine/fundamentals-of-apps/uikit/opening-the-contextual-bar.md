# Opening the Contextual Bar

Apps are allowed to open a contextual bar with UIKit content. It works just like a modal: you pass a BlockBuilder object containing the content you want to display on the surface and call the following methods:

```typescript
        // for creating a new contextual bar
        await modify.getUiController().openContextualBarView(blocks, { triggerId }, user);
        // for updating a existing contextual bar
        await modify.getUiController().updateContextualBarView(blocks, { triggerId }, user);
```

It does need a valid `IUIKitInteractionParam` object with the `triggerId` and the `IUser` calling the from the user calling the method.

A sample application opening the contextual bar would consist of 2 main parts: a slashcommand from where we can get a valid `triggerId` and the function that opens the contextual bar using it.\\

You can clone the app and test it in your own Rocker.Chat server:\
[https://github.com/RocketChat/apps-contextual-bar-open-example](https://github.com/RocketChat/apps-contextual-bar-open-example)

{% code title="ContextualBarExample.ts" %}
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

// This is the slashcommand that opens the contextual bar:
// - first we get the triggerId  to open the surface (without this it would not be possible to open the contextual bar) ([1])
// - then we create the blocks we will render inside the contextual bar ([2])
// - then call the method that opens the contextual bar ([3]).
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

        await modify.getUiController().openContextualBarView(contextualbarBlocks, { triggerId }, user); // [3]
    }
}

// This method creates the blocks that will be rendered inside the contextual bar.
// It consisist of:
// - a message that presents the current date-time ([4])
// - a button that updates the date-time shown in the message ([5])
// - the contextual bar structure containing its title and a submit button ([6])
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

// Here in the main class we setup the whole app:
// - first we provide the slashcommand we will use ([7])
// - then we listen to when the button on [5] is pressed ([8])
// - we update the contextual bar's content ([9])
// - listen for when the user presses the 'submit' button ([10])
// - get the content (date-time) from the contextual bar ([11])
// - logs the data to the console ([12])
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
```
{% endcode %}
