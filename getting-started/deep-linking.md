# Deep linking

Rocket.Chat's deep linking feature allows mobile and desktop clients to handle links specifically designed for the Rocket.Chat application. This is achieved using a unique URL that the applications are registered to handle. The deep linking feature enhances the user experience by providing shortcuts to specific content or actions within the Rocket.Chat application.

There are two types of prefixes available for deep linking:

1. **Go Links**: These are links that start with `https://go.rocket.chat`. They are universal and work across web, mobile, and desktop clients.
2. **Alternative Prefix**: This prefix is `rocketchat://` and is only handled by mobile and desktop clients.

In all examples, `https://go.rocket.chat/` is interchangeable with `rocketchat://`.

* **Adding a Server**: Deep links can be used to add a server to your client in one click, simplifying the deployment process. You can create a universal link that will add the server to the clients.
* **Authentication Links**: These links start with `https://go.rocket.chat/auth` and can include the host of the server, the token of the user to be authenticated, and the id of the user to be authenticated. This allows you to create a link that not only directs the user to the server but also automatically logs them in.

<mark style="color:blue;">Examples:</mark>

Link directly to the server:

```
https://go.rocket.chat/auth?host=open.rocket.chat
```

Link directly to the server and authenticate:

```
https://go.rocket.chat/auth?host=foo.bar.com&token=123abc&userId=1234abcd
```

* **Room Links**: You can link directly to a room using deep links that start with `https://go.rocket.chat/room`. These links require the host of the server and the rid (room id) of the room to be opened. Optionally, you can also include the path URL to be opened on the web.

<mark style="color:blue;">Example:</mark>

```
https://go.rocket.chat/room?host=open.rocket.chat&rid=GENERAL&path=channel/general
```

* **Invite Links**: You can invite a user to a room through a link. These links start with `https://go.rocket.chat/invite` and require the host of the server and the path URL with the token param to be authenticated and opened on the web.

<mark style="color:blue;">Example:</mark>

```
https://go.rocket.chat/invite?host=open.rocket.chat&path=invite/xyzxyZ
```

* **Conference Call Links**: You can start a conference call using a deep link with the provider's information. These links start with `https://go.rocket.chat/conference` and require the host of the server, the path URL with the `conferenceId` param, the path URL of the call, and the name of the call provider.

<mark style="color:blue;">Example:</mark>

{% code overflow="wrap" %}
```
https://go.rocket.chat/conference?host=open.rocket.chat&path=conference/12345?callUrl=https://providerHost/someinfoOrPath&callProvider=providerName
```
{% endcode %}

Rocket.Chat's deep linking feature provides a seamless way to navigate to specific content or perform specific actions within the application, enhancing the user experience and making it easier for users to interact with the platform.
