# Chat Engine in iframe

One approach of incorporating Rocket.Chat's chat capabilities into your application is through embedding it within an iframe. This method allows you to integrate the original Rocket.Chat's chat interface seamlessly into your existing front-end system.&#x20;

## Considerations

Before proceeding with the iframe embed, these settings need to be configured in your workspace based on your desired implementation.

{% hint style="info" %}
* Navigate to **Administration** -> **Workspace** -> **Settings** -> **General**
  * Switch on **Enable Send** and **Enable Receive** of iframe events under **Iframe Integration**.: Allows Rocket.Chat to send and receive events to iframes embedded within it. This is crucial for seamless communication and interaction between the Rocket.Chat workspace and the content within iframes.
  * Disable **Restrict access inside any Iframe:** Removes restriction for your Rocket.Chat workspace to be embedded within an iframe on another website. Ideally, this should be configured for security purposes.
  * Turn on **Enable CORS** under **REST API:**  Allows API Requests from other domains to be allowed on your Rocket.Chat server. This is only necessary if REST API calls are to be made from the front end. It is recommended to call from your backend.
* If you want the top header to be hidden within your iframe embed, Navigate to **Administration** -> **Workspace** -> **Settings** -> **Layout** -> **User Interface** and disable **Show top navbar in embedded layout**.
{% endhint %}

{% hint style="warning" %}
API calls to Rocket.Chat should typically be made from the server side and should be available only to app-authenticated users.
{% endhint %}

## Procedure

Establishing a connection between your application and Rocket.Chat utilizes the use of Rocket.Chat REST API for authentication and other necessary operations.

### Authentication

You can choose to authenticate users within your application. Generating a [Personal Access Token (PAT)](../reference/api/rest-api/endpoints/core-endpoints/users-endpoints/create-users-token.md) for a system user with an admin role is recommended. This token is used for authentication purposes, rather than logging in with the system account credentials every time, providing a secure way to access the chat functionality without exposing the system account credentials.

Learn more about iframe authentication [here](../customize-and-embed/iframe-integration/configuring-iframe-auth/).

### Embedding the iframe

To embed the Rocket.Chat chat interface within an iframe, you need to include the appropriate HTML code in your application. The following example demonstrates the basic structure of the iframe.

```html
<iframe src="https://<your-rocket-chat-instance.com>/channel/<channel-name>?layout=embedded"
        width="800px"
        height="500px"
        frameborder="1"
        allow="camera;microphone"
        sandbox="allow-same-origin allow-scripts allow-popups allow-forms">
</iframe>
```

Make sure to replace the `<your-rocket-chat-instance.com>` and `<channel-name>` with your Rocket.Chat workspace URL and the specific channel you want to embed.

When embedding the chat interface using an iframe, you can specify the iframe source to point to a desired channel in the embed layout mode. The embed URL format is seen below.

```
https://<your-rocket-chat-instance.com>?layout=embedded // Embeds the entire workspace
https://<your-rocket-chat-instance.com>/channel/<channel-name>?layout=embedded // Embeds a specific channel
```

Learn more about [iframe integration](../customize-and-embed/iframe-integration/) and [embedded layout](../customize-and-embed/embedded-layout.md).

### Handling User Authentication

You can choose to authenticate users based on details from your application or create Rocket.Chat users on the fly to authenticate for chat capabilities.

After [creating a user](../reference/api/rest-api/endpoints/core-endpoints/users-endpoints/create-user.md) and getting their [user token](../reference/api/rest-api/endpoints/core-endpoints/users-endpoints/create-users-token.md) with the API endpoints, utilize the iframe's `onload` event(when the iframe loads) and the `postMessage` API to pass the users `auth-token` into the iframe to be used for authentication in the embedded chat interface.&#x20;

Here is an example of how to handle the `onload` event and pass the authentication token:

<pre class="language-javascript"><code class="lang-javascript">const iframe = document.querySelector('iframe');

iframe.onload = function() {
  // Get the authentication token
  const authToken = "user-auth-token";

  // Pass the authentication token to the embedded chat interface
  iframe.contentWindow.postMessage({
    externalCommand: 'login-with-token',
<strong>    token: authToken
</strong><strong>  }, '*');
</strong>};
</code></pre>

Replace the `user-auth-token` with the actual authentication token of the user obtained earlier. This code snippet demonstrates how to retrieve the iframe element and tie the `onload` iframe event to send the auth token to the embedded chat interface using the `postMessage` API.

A list of Rocket.Chat iframe embed commands can be seen [here](../customize-and-embed/iframe-integration/iframe-integration-sending-commands.md).

### **Customizing the Embedded Layout**

If you wish to customize the layout of the chat interface, you can consider building a custom frontend integration with Chat Engine as described in this section [chat-engine-with-custom-frontend.md](chat-engine-with-custom-frontend.md "mention").

When a channel is specified, and a user is authenticated, the embedded iframe is displayed without the Rocket.Chat sidebar and channel topbar.

<figure><img src="../.gitbook/assets/RocketChat Iframe embed.png" alt=""><figcaption><p>Rocket.Chat Iframe embed</p></figcaption></figure>

{% hint style="info" %}
**Considerations**

* Use Rocket.Chat [Roles ](https://docs.rocket.chat/setup-and-configure/roles-in-rocket.chat)against users to restrict access to other channels.
* Authenticate users before allowing them to access the chat interface and perform actions.
* Implement appropriate measures to prevent cross-site scripting (XSS) attacks and protect user data.
* Use responsive design techniques for a better user experience.
{% endhint %}
