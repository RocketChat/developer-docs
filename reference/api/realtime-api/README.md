# Realtime API

The Rocket.Chat real-time API allows developers to integrate Rocket real-time messaging and collaboration features in their applications. It utilizes WebSockets, a technology that enables real-time communication between a client (your application) and the Rocket.Chat server. By leveraging this API, you can create dynamic, interactive experiences within your application, enabling users to send and receive messages, participate in live chats, and access various collaboration features.&#x20;

To get started with the Rocket.Chat Real-Time API, point your client to the WebSocket of the server you want to connect to:

```
wss://[ABC.DOMAIN.COM]/websocket
```

{% hint style="info" %}
For localhost, use `ws://localhost:3000/websocket.`
{% endhint %}

The API encompasses two integral components: [Method Calls](method-calls/) and [Subscriptions](subscriptions/), seamlessly supported within the WebSocket connection.&#x20;

To ensure streamlined functionality within a single connection, we leverage RPC (Remote Procedure Call) using the following format:

```javascript
{
    "msg": "type-of-communication",
    "id": "unique-id",
    ... // per call defined data
}
```

The "`type-of-communication`" is defined based on its purpose:

* [Method Calls](method-calls/): `method`
* [Subscriptions](subscriptions/): `sub`

## Connect to the WebSocket

Before requesting any [method calls](method-calls/) and [subscriptions](subscriptions/), it is necessary to send a connect message. This connect message is an initial step to establish the connection and prepare for subsequent requests.

```json
{
    "msg": "connect",
    "version": "1",
    "support": ["1"]
}
```

{% hint style="info" %}
The server periodically sends a "`ping`" message, and it's essential to respond with a "`pong`" message to maintain the connection. Failure to respond appropriately will result in the server closing the connection.
{% endhint %}

```json
{
    "msg": "pong"
}
```

## Resources

* [rocketchat-ddp-listener](https://github.com/JSzaszvari/rocketchat-ddp-listener):  A basic example script that uses the 'ddp' NodeJS package to subscribe to the Realtime-API stream of a Group/Channel.
* [Rocket.Chat.RealTime.API.RxJS](https://github.com/inf3cti0n95/Rocket.Chat.RealTime.API.RxJS) Abstraction for Utilizing Rocket.Chat's [Realtime API](https://rocket.chat/docs/developer-guides/realtime-api) Methods with [RxJS](http://reactivex.io/rxjs/).&#x20;
* [rocketchat-async](https://github.com/hynek-urban/rocketchat-async) : asyncio-based Python wrapper for the Rocket.Chat Realtime API
