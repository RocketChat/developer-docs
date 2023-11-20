# Apps-Engine UI Guidelines

With the Apps-Engine UIKit, we have seen how to create the interactions in our apps displayed on the Rocket.Chat UI. Follow these guidelines for any interface that you are creating for your Rocket.Chat app using the Apps-Engine.

## Surface types

There are two surface types:

1. **Simple**: Examples like menus that can contain only the predefined list of menu items
2. **Complex**: Examples like contextual bars and modal views can use all available [UIKit components](building-blocks.md) to build the intended user experience.

## User menu

The user menu contains items specific to the user such as status and preferences. Every item on this menu should relate to a user.

* **Do** add only user-specific items to this menu

<figure><img src="../../../.gitbook/assets/1.png" alt=""><figcaption><p>User menu visual guide</p></figcaption></figure>

## Room kebab menu

The room kebab menu is located at the top-right side of any [Rocket.Chat Room](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms).

* This menu opens up a contextual bar and not a modal.
* Items on this menu must relate to or affect the current room or its context in some way.
* **Don't** include icons or use emojis in item labels.

<figure><img src="../../../.gitbook/assets/2.png" alt=""><figcaption><p>Room kebab menu UI guide</p></figcaption></figure>

## Message kebab menu

The message kebab menu can be seen on the right side of a message when hovered upon on a Desktop or long-pressed on a Mobile device.

* The message kebab menu is reserved exclusively for items that affect the selected message.
* Only Rocket.Chat core actions can use icons.
* **Don't** include icons or emojis anywhere inside the item label.

<figure><img src="../../../.gitbook/assets/3.png" alt=""><figcaption><p>Message kebab menu UI guide</p></figcaption></figure>

## Chat messages

* Make messages very clear and brief.
* **Do** use an emoji if only they help get the intended message across.
* **Don't** send messages on a user's behalf.
* **Don't** over-communicate or use emojis excessively.

<figure><img src="../../../.gitbook/assets/4.png" alt=""><figcaption><p>Chat message UI Guide</p></figcaption></figure>

## Slash commands

Slash commands are usually the simplest ways users can interact with installed apps.

* Slash command descriptions should appear next to the command when typed in the message composer.
* Commands must have hyphens between words and include a description.

<figure><img src="../../../.gitbook/assets/5.png" alt=""><figcaption><p>Slash commands UI Guide</p></figcaption></figure>

* All apps using a slash command must have a `/help` command showing the possibilities of the app and its commands.

## Contextual bars

Apps can utilize the contextual bar surface to offer information and actions to the user.

* Contextual bars must contain a corresponding item in the [room kebab menu](apps-engine-ui-guidelines.md#room-kebab-menu).
* Contextual bar titles must use sentence case capitalization eg: `Google Calendar settings`, not `Google Calendar Settings.`
* **Don't** use images, such as app icons, inside the contextual bar header.
* **Don't** use the title case in the contextual bar header.
* **Do** use sentence case in contextual bar header.

<figure><img src="../../../.gitbook/assets/6.png" alt=""><figcaption><p>Contextual bar UI Guide</p></figcaption></figure>

## Modals

Apps utilize modal dialogs to present information and actions to the user. Use [Contextual bars](apps-engine-ui-guidelines.md#contextual-bars) for more complex and involved interactions.

As a default setting, the app logo asset will be presented in the modals that are linked to the corresponding app.

* **Don't** use modals without the app name in the tagline.
* **Do** use the app name in the modal tagline.

<figure><img src="../../../.gitbook/assets/7.png" alt=""><figcaption><p>Modals UI Guide</p></figcaption></figure>

## App (bot) username

If your app has an associated bot user, the username of that user must be identical to the app name except with a hyphen replacing any spaces in the app name. For example, if the app is a Google Calendar app, the bot username must be _`@google-calendar`,_ not _`@google-calendar.bot`_ or any other variation.

With these guidelines in mind, you can create functional apps that leverage the UIKit components and provide helpful user interactions. To fully apply these functionalities, you need to define the configuration and permissions for your app so that it can perform actions such as sending messages or modifying settings. Let's move on to the next sections to understand the configuration details.
