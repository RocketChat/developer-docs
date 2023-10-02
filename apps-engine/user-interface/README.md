---
description: Follow the guidelines to make your apps beautiful.
---

# User Interface

### About Apps Engine UIKit

* What you use to allow apps to interact with the UI is called the UIkit, which is a series of blocks that apps can compose, and can be mapped to components that will be displayed on the screen.&#x20;
* UIKit is a set of components used in the Apps Engine that allow apps to interact with Rocket.Chat's UI. In the upcoming sections, you will find more details on how to use those components.&#x20;
* Everything you see below in this screenshot is a UI block, and these interactions are managed via a UI controller in the Apps Engine.&#x20;
* We provide limited components for the app interface to be built, but we provide one component that adheres to Rocket.Chat design specifications. So, it will look just like Rocket.Chat, without breaking the UX continuity for users.&#x20;
* That’s one of the upsides of using the UIkit provided by Rocket.Chat. Most of these interactions can be made mobile responsiveness as well, without any additional coding. These UI components can be displayed on the web and mobile alike; Rocket.Chat provides the code for that.&#x20;
* All you have to do is define the interaction and call the components as needed.&#x20;
* There’s a playground where you can try out different blocks, and you just copy and paste it into your app code.&#x20;
* After you build the block objects & modal objects, they will interact with the UI via the UI controller which is inside the modify accessor. `getUIController()` is the method, which then has other methods.&#x20;

The `openSurfaceView` comprises the methods for calling the contextual bar and the modal. You just have to build your view — either the modal or contextual bar. Apps Engine and Rocket.Chat will be able to tell which one you’re trying to display to the user. This will be defined in the UIKitSurfaceType.&#x20;

### Displaying an overlay popup

For an app to be able to interact with the UI, we need user consent. Apps can’t just randomly display an overlay popup.&#x20;

* TriggerID - whenever a user interacts with the app, the app can get a trigger ID, which is more like a password that is required in all the methods in the UI controller, so that the UI components will be shown. It will only work if the app has a valid trigger ID issued by Rocket.Chat. Interactions from the user will provide a valid trigger ID.&#x20;
* If a valid trigger ID is not provided, the method call will fail silently and the desired action will not take place.

### Handling user interactions

* When a user interacts with any UI components, it triggers other interactions. The `IUIKitInteractionHandler` is a handler for after a message is sent. All the methods then become available to the app.&#x20;
* Based on the UI component, the app receives an interaction of the specified type, and the app gets the context of what the interaction was, what data was filled, the inputs provided by the user, and so on.&#x20;
* Depending on the app’s functionality and flow, the user might have to input some data — such as filling out a form. The `IUIKitInteractionHandler` helps you handle user interactions by capturing the data in the backend.&#x20;

### Action buttons

* Currently, it’s possible for apps to register action buttons in different places in the UI — in the room menu, the kebab menu, the message options, the message composer box options, and so on.&#x20;
* The `UIActionButtonContext` helps you place the action block contextually across several places within Rocket.Chat.&#x20;

Read the documents in the upcoming sections for further details on each component of the UIKit and how you can leverage them for your app. \
