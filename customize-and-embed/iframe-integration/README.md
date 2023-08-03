# Iframe Integration

Rocket.Chat offers a multitude of customization and embedding options to integrate its functionalities into your existing digital ecosystem seamlessly. One such powerful feature is the iframe integration. This feature allows you to embed Rocket.Chat within an external web page or application interface, providing a unified and consistent user experience.

The iframe integration not only enables you to incorporate Rocket.Chat into your application but also allows you to authenticate users with your own login page, replacing the need for Rocket.Chat's login. This ensures a smooth and uninterrupted user journey, enhancing user satisfaction and engagement.

To utilize the iframe integration, you need to follow a few simple steps:

1. **User Authentication:** To authenticate users via iframe integration, navigate to **Administration > Workspace > Settings > Accounts > Iframe**. Toggle on the **Enabled** option and proceed with [configuring the iframe auth](configuring-iframe-auth/). This will allow you to set up user authentication through your own login page.
2. **Embedding Rocket.Chat:** Depending on your needs, you can embed Rocket.Chat in your application using an iframe. This provides a seamless integration of Rocket.Chat's features into your application's interface.
3. **Event Listening:** While embedding Rocket.Chat in your app, you can listen to events. To do this, navigate to **Administration > Settings > General > Iframe Integration.** Here, you can enable send (events) or receive (commands) depending on your needs. This feature allows your application to interact with Rocket.Chat, providing a dynamic and interactive user experience.

By leveraging this feature, you can significantly enhance the communication capabilities of your application, driving user engagement and satisfaction.

{% content-ref url="iframe-events.md" %}
[iframe-events.md](iframe-events.md)
{% endcontent-ref %}

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

{% content-ref url="../embedded-layout.md" %}
[embedded-layout.md](../embedded-layout.md)
{% endcontent-ref %}
