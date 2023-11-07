# Apps-Engine User Interface

Along with using slash commands and handling events, another way to extend an app's functionality is to add user interactions such as buttons or menus to perform some action. Apps-Engine's UIKit is a set of components that allow apps to interact with Rocket.Chat's UI. It provides a series of block objects that you can use and map to the components that will be displayed on the screen.

## Features of UIKit

* Rocket.Chat provides limited components for the app interface to be built and one component adheres to the Rocket.Chat design specifications. So, it will look just like Rocket.Chat, without breaking the UX continuity for users.&#x20;
* Most of the interactions can be made mobile responsive as well, without any additional coding. This is one of the benefits of using the UIkit provided by Rocket.Chat. All you have to do is define the interaction and call the components as needed.&#x20;
* After you build the block objects, they will interact with the UI via the UI controller which is inside the modify accessor called `getUiController()`.&#x20;
* `openSurfaceView` has the methods for calling the contextual bar and the modal. You just have to build your view — either the modal or contextual bar. Apps-Engine and Rocket.Chat will be able to tell which one you’re trying to display to the user. This will be defined in `UIKitSurfaceType`.&#x20;

Some of the user interactions that you can define are as follows:

### Displaying an overlay popup

For an app to be able to interact with the UI, we need user consent.&#x20;

* **TriggerID -** whenever a user interacts with the app, the app can get a trigger ID, which is like a password that is required in all the methods in the UI controller, so that the UI components will be shown. It will only work if the app has a valid trigger ID issued by Rocket.Chat. Interactions from the user will provide a valid trigger ID.&#x20;
  * If a valid trigger ID is not provided, the method call will fail silently and the desired action will not take place.

### Handling user interactions

* When a user interacts with any UI components, it triggers other interactions. The `IUIKitInteractionHandler` is a handler for after a message is sent. All the methods then become available to the app.&#x20;
* Based on the UI component, the app receives an interaction of the specified type, and the app gets the context of what the interaction was, what data was filled, the inputs provided by the user, and so on.&#x20;
* Depending on the app’s functionality and flow, the user might have to input some data — such as filling out a form. `IUIKitInteractionHandler` helps you handle user interactions by capturing the data in the backend.&#x20;

### Action buttons

* Apps can register action buttons in different places in the UI — in the room menu, the kebab menu, the message options, the message composer box options, and so on.&#x20;
* The `UIActionButtonContext` helps you place the action block contextually across several places within Rocket.Chat.&#x20;

Read the upcoming sections for further details on each component of the UIKit and how you can leverage them for your app.&#x20;
