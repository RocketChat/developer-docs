# Embedded Layout

The embedded layout feature of Rocket.Chat is a powerful tool for creating focused, immersive communication experiences within a single channel or room. When combined with Iframe integration, it allows for seamless interaction with a specified channel embedded within an application.

With Iframe integration, you can log in the user and display a specified channel embedded within your application. This means the user can interact with the channel as if they were on the Rocket.Chat platform, but within the context of your own application. This seamless integration provides a cohesive user experience, allowing for focused communication and collaboration.

When embedding Rocket.Chat in your site, you can change the layout by adding `?layout=embedded` after your server URL. For example, [_https://open.rocket.chat/channel/general?layout=embedded_](https://open.rocket.chat/channel/general?layout=embedded). It changes the workspace layout to a more "simplistic" view, hiding the left sidebar menu and room top navbar.

To **enable the top navbar of the room in the embedded layout,**&#x20;

* Navigate to **Administration > Workspace > Settings > Layout > User Interface**&#x20;
* &#x20;Enable **Show top navbar in embedded layout**.

When a URL is set to embedded mode, the view will be restricted to a single [room](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms), as the user won't have access to the channel lists. When combined with [Iframe integration](iframe-integration/), the embedded layout works as expected because you can authenticate the user and only show a specified channel embedded in the application.

You can test this feature by going to  [_https://open.rocket.chat/channel/general?layout=embedded_](https://open.rocket.chat/channel/general?layout=embedded).

{% hint style="warning" %}
To prevent users from accessing other channels, relying on the embedded layout alone won't suffice. Users could alter the URL using browser tools. Therefore, it's recommended to edit the user permissions to restrict access to other channels.
{% endhint %}

Whether you're looking to enhance the communication capabilities of your application or provide a distraction-free environment for focused discussions, the embedded layout feature is a valuable addition to your toolkit.
