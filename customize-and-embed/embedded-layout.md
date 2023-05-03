# Embedded Layout

When embedding Rocket.Chat in your site, you can change the layout by adding `?layout=embedded` after your server URL. For example, [https://open.rocket.chat/channel/general?layout=embedded](https://open.rocket.chat/channel/general?layout=embedded). It changes the layout of Rocket.Chat to a more "simplistic" view, hiding the left sidebar with the channel lists and account management buttons.&#x20;

Additionally, to **enable the top navbar of the room in the embedded layout,**&#x20;

* Navigate to **Administration > Workspace > Settings > Layout > User Interface**&#x20;
* &#x20;Enable **Show top navbar in embedded layout**.

When a URL is set to embedded mode, the view will be restricted to a single [room](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms), as the user won't have access to the channel lists. When combined with [Iframe integration](iframe-integration/), the embedded layout works as expected because you can already login the user and only show a specified channel embedded in the application.

You can test this feature by going to [https://open.rocket.chat?layout=embedded](https://open.rocket.chat).

{% hint style="info" %}
To prevent users from accessing other channels, relying on the embedded layout alone won't suffice. Users could alter the URL using browser tools. Therefore, it's recommended to edit the user permissions to restrict access to other channels.
{% endhint %}
