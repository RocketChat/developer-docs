# Iframe Integration

An iframe integration in Rocket.Chat is a way to embed Rocket.Chat within an external web page or application interface. You can authenticate users with your login page instead of Rocket.Chat's login via iframe integration.

You can embed Rocket.Chat in your application depending on your needs using an iframe.

To authenticate users via iframe integration,&#x20;

* Navigate to **Administration > Settings > Accounts > Iframe**
* Toggle on the **Enabled** option and proceed with [configuring the iframe auth](configuring-iframe-auth/).

{% content-ref url="configuring-iframe-auth/" %}
[configuring-iframe-auth](configuring-iframe-auth/)
{% endcontent-ref %}

To listen to events while embedding Rocket.Chat in your app,

* Navigate to **Administration > Settings > General > Iframe Integration.**
* Enable send (events) or receive (commands) depending on your needs.

{% content-ref url="iframe-events.md" %}
[iframe-events.md](iframe-events.md)
{% endcontent-ref %}

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

{% content-ref url="../embedded-layout.md" %}
[embedded-layout.md](../embedded-layout.md)
{% endcontent-ref %}
