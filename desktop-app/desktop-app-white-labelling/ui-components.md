# UI Components

Rocket.Chat's UI components collectively form the visual and interactive foundation of the server. By customizing these components, you can align the interface with your organization's branding, enhance user experience, and introduce specialized features. This guide provides comprehensive descriptions and illustrative usage examples for each UI component in Rocket.Chat. Its purpose is to enhance development ease and prevent redundant contributions of similar components with conflicting styles and usage patterns.&#x20;

### Side Nav

The Rocket.Chat side nav UI component renders the side navigation menu for the Rocket.Chat server. The component takes in a few props, including the current user's data, the list of channels, and the list of rooms. The component uses this data to render a list of navigation items, each of which links to a different page in the Rocket.Chat app. The component also includes a search bar that users can use to find channels and rooms.

{% hint style="info" %}
If you have any ideas for how to improve the Rocket.Chat UI components, see [participate-in-rocket.chat-development](../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/ "mention").
{% endhint %}
