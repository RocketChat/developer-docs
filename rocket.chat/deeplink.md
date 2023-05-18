# Deeplink

## General information

Our mobile and desktop clients have implemented deep linking that will allow them to handle links meant for Rocket.Chat.

This is done using a special URL that the applications are registered to handle.

There are two prefixes available:

* `https://go.rocket.chat`
* `rocketchat://`

We call `https://go.rocket.chat` links go links. Links here will work across web, mobile, and desktop clients.

The alternative will only be handled by mobile and desktop clients.

In all examples below `https://go.rocket.chat/` is interchangeable with `rocketchat://`

## Authentication

These links can be used for adding a server to your client in one click. This makes it easier for deployment. You then have a universal link that will add to the clients.

You can also include credentials to make it add the server and auto-log them in.

Authentication links start with: `https://go.rocket.chat/auth`

**Params:**

* host: The host of the server;
* token (optional): The token of the user to be authenticated;
* userId (optional): The id of the user to be authenticated;

**Examples:**

Link directly to the server:

```
https://go.rocket.chat/auth?host=open.rocket.chat
```

Link directly to the server and authenticate:

```
https://go.rocket.chat/auth?host=foo.bar.com&token=123abc&userId=1234abcd
```

## Channel / Group / DM

You can also link directly to a room.

These links start with: `https://go.rocket.chat/room`

**Params:**

* host: The host of the server;
* rid: The rid of the room to be opened;
* path (optional): The path URL to be opened on the web;

**Example:**

```
https://go.rocket.chat/room?host=open.rocket.chat&rid=GENERAL&path=channel/general
```

## Invite

You can invite a user to a room through a link.

These links start with: `https://go.rocket.chat/invite`

**Params:**

* host: The host of the server;
* path: The path URL with the token param to be authenticated and opened on the web;

**Example:**

```
https://go.rocket.chat/invite?host=open.rocket.chat&path=invite/xyzxyZ
```

## Conference

You can start a conference call using a deep link with the provider's information.

These links start with: `https://go.rocket.chat/conference`

**Params:**

* host: The host of the server;
* path: The path URL with the `conferenceId` param;

**Query Params:**

* callUrl: The path URL of the call;
* callProvider: The name of the call provider;

**Example:**

```
https://go.rocket.chat/conference?host=open.rocket.chat&path=conference/12345?callUrl=https://providerHost/someinfoOrPath&callProvider=providerName
```
