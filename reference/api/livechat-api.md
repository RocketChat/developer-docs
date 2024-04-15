# Livechat Widget API

The Livechat Widget API allows developers to integrate Livechat widget functionalities into their apps seamlessly. The code must be after the[ Livechat Widget installation](https://docs.rocket.chat/use-rocket.chat/omnichannel/livechat-widget-installation) script and wrapped as a callback of `RocketChat();` function.

{% hint style="info" %}
You can call multiple Livechat Widget APIs on the same page. The Widget API information is stored in the local storage of the browser.
{% endhint %}

## Methods

### Set custom field

To set a custom field for a visitor, you can use the following:

{% code overflow="wrap" %}
```javascript
RocketChat(function() {
    this.setCustomField('fieldName1', 'Any value you want to store');
    this.setCustomField('fieldName2', 'A value set just once', false); // you can pass false as the third parameter to not overwrite an already set value
});
```
{% endcode %}

### Set theme options

To change the color of the online status on the Livechat widget, use the following:

{% code overflow="wrap" %}
```javascript
RocketChat(function() {
    this.setTheme({
        color: '#04436A', // widget title background color
        fontColor: '#FFFFFF', // widget title font color
        iconColor: '#1d74f5', // widget icon color
        title: "Welcome to Rocket.Chat", // default widget title when the status of service is online
        offlineTitle: "Service is offline", // default widget title when the status of service is online
        position: 'right', // Already mentioned, can be left or right
        background: 'red', // Already mentioned, follows CSS standards
        guestBubbleBackgroundColor: 'blue', // Changes the background color of the message bubble for the guest. Accepts simple colors like hexadecimal and valid color names.
        agentBubbleBackgroundColor: 'green', // Changes the background color of the message bubble for the agent. Accepts simple colors like hexadecimal and valid color names.
        hideGuestAvatar: true, // Hides/shows guest avatar. It can be either true or false. Default is false.
        hideAgentAvatar: false, // Hides/shows agent avatar. It can be either true or false. Default is true.
    });
});
```
{% endcode %}

{% hint style="info" %}
The following theme options are exclusively available to workspaces subscribed to any of Rocket.Chat's [premium plans](https://docs.rocket.chat/readme/our-plans):

* agentBubbleBackgroundColor
* guestBubbleBackgroundColor
* background
* hideAgentAvatar&#x20;
* hideGuestAvatar&#x20;
* position
{% endhint %}

### Remove theme options

To remove the theme options, set the field value as `undefined`. Note that omitting the field itself does not remove the customization value.

```javascript
RocketChat(function() {
    this.setTheme({
        color: undefined,
        fontColor: '#FFFFFF',
    });
});
```

### Assign chats to a specific department

To automatically assign a Livechat widget to a specific department (for example, to use a unique Livechat widget on more than one website), use the following :

```javascript
RocketChat(function() {
    this.setDepartment('FILL HERE DEPARTMENT NAME - case sensitive');
});
```

### Set visitor token

To set an external token for a visitor, use this:

```javascript
RocketChat(function() {
    this.setGuestToken('FHwaLnp8fzjMupSAj');
});
```

### Set name field

To set the visitor name field, use this:

```javascript
RocketChat(function() {
    this.setGuestName('visitor name');
});
```

### Set email field

To set the visitor email field, use this:

```javascript
RocketChat(function() {
    this.setGuestEmail('sample@rocket.chat');
});
```

### Register visitor

To register the visitor without using the registration form, use this:

```javascript
RocketChat(function() {
    this.registerGuest({
        token: 'FHwaLnp8fzjMupSAj', // The token field is not required. If it is not passed, a new token will be generated
        name: 'visitor Name',
        email: 'sample@rocket.chat',
        department: 'my_department', // The department field is not required,
        customFields: [ // The customFields field is not required. If it is passed it needs to be an Array, where each item needs to be an object with key and value fields
            {key:  'my_custom_field_a', value: 'my_custom_field_a_value', overwrite: true},
            {key:  'my_custom_field_b', value: 'my_custom_field_b_value', overwrite: true}
        ]
    });
});
```

### Set Guest Metadata ![](../../.gitbook/assets/Premium.svg)

To determine a list of attributes and their corresponding values for a guest:

<pre class="language-javascript"><code class="lang-javascript"><strong>RocketChat(function () {
</strong>    this.setGuestMetadata({
        name: 'Johnnie Walker',
        serviceID: '3455566'
    });
});
</code></pre>

{% hint style="info" %}
This method is essential when using an [external service to send livechat trigger messages](https://docs.rocket.chat/use-rocket.chat/omnichannel/livechat-triggers#omnichannel-livechat-trigger-actions).
{% endhint %}

### Set Language for Widget

To select a language for the widget, use this:

```javascript
RocketChat(function() {
    this.setLanguage('af');
});
```

{% hint style="info" %}
See supported languages [here](https://github.com/RocketChat/Rocket.Chat/tree/develop/packages/livechat/src/i18n).
{% endhint %}

### Set a default Agent before starting a new conversation

Set a specific agent before the conversation starts. Use this to set up:

```javascript
RocketChat(function() {
    this.setAgent({
        _id: 'h24yNtyoCmvp96wgt',
        username: 'rocket.chat',
  });
});
```

### Initialize the widget by configuring all available properties in just one call

To configure all the settings in just one method, use this:

```javascript
RocketChat(function() {
    this.initialize({
        theme: {
            color: '#04436A',
            fontColor: '#FFFFFF',
            iconColor: '#1d74f5',
            title: "Welcome to Rocket.Chat",
           offlineTitle: "Service is offline",
           hideGuestAvatar: false, 
           hideAgentAvatar: true
        },
        department: 'sales',
        guestToken: 'FHwaLnp8fzjMupSAj',
        language: 'en',
        setGuestMetadata: { name: 'Johnnie Walker', serviceID: '3455566'},
  });
});
```

### Change widget visibility

You can either hide or show widget in your application. To hide the widget use this:

```javascript
RocketChat(function() {
    this.hideWidget();
});
```

To show widget, use this:.

```javascript
RocketChat(function() {
    this.showWidget();
});
```

### Change the widget window state

You can either open or close the widget on your website. To open the widget by default, use this:

```javascript
RocketChat(function() {
    this.maximizeWidget();
});
```

To close the widget, use this:

```javascript
RocketChat(function() {
    this.minimizeWidget();
});
```

### Set Business Unit to filter departments on Registration page

<figure><img src="../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Assign a business unit to a widget instance so that the widget will only allow the visitors to select departments connected to that particular business unit on the widget's registration form.

{% hint style="info" %}
Enterprises need to deal with hundreds of business units in the same workspace, and each Business Unit represents a specific website where Live Chat is installed. Therefore, once a BU is set, only departments associated with the current BU set should be available on the Live Chat Registration Form.
{% endhint %}

```javascript
RocketChat(function() {
    this.setBusinessUnit('LnM2rzbknjYSkkd5p');
});
```

To clear any connected business unit on the widget, use this:

```javascript
RocketChat(function() {
    this.clearBusinessUnit();
});
```

### Hide system messages ![](../../.gitbook/assets/Premium.svg)

You can hide specific system messages in the livechat widget conversation. Use the method as follows:

```javascript
RocketChat(function() {
  this.setHiddenSystemMessages(
    ['uj' // User joined
     'ul' // User left
     'livechat-close' // Chat closed
     'livechat-started' // Chat started
     'livechat_transfer_history' // Chat transferred ]
  )}
);
```

## Events

### onChatMaximized

Fired when the chat widget is maximized.

```javascript
RocketChat(function() {
    this.onChatMaximized(function() {
        // do whatever you want
        console.log('chat widget maximized');
    });
});
```

### onChatMinimized

Fired when the chat widget is minimized.

```javascript
RocketChat(function() {
    this.onChatMinimized(function() {
        // do whatever you want
        console.log('chat widget minimized');
    });
});
```

### onChatStarted

Fired when the chat is started (when the first message is sent).

```javascript
RocketChat(function() {
    this.onChatStarted(function() {
        // do whatever you want
        console.log('chat started');
    });
});
```

### onChatEnded

Fired when the chat is ended either by the agent or the visitor.

```javascript
RocketChat(function() {
    this.onChatEnded(function() {
        // do whatever you want
        console.log('chat ended');
    });
});
```

### onPrechatFormSubmit

Fired when the pre-chat form is submitted.

```javascript
RocketChat(function() {
    this.onPrechatFormSubmit(function(data) {
        // data is an object containing the following fields: name, email and deparment (the department _id)

        // do whatever you want
        console.log('pre-chat form submitted');
    });
});
```

### onOfflineFormSubmit

Fired when the offline form is submitted.

```javascript
RocketChat(function() {
    this.onOfflineFormSubmit(function(data) {
        // data is an object containing the following fields: name, email and message

        // do whatever you want
        console.log('offline form submitted');
    });
});
```

### onWidgetHidden

Fired when the widget is hidden.

```javascript
RocketChat(function() {
    this.onWidgetHidden(function(data) {
        // do whatever you want
        console.log('chat widget hidden');
    });
});
```

### onAssignAgent

Fired when an agent is assigned to the chat.

```javascript
RocketChat(function() {
    this.onAssignAgent(function(data) {
        // data is an object containing the following fields: name, username and status

        // do whatever you want
        console.log('Agent assigned');
    });
});
```

### onWidgetShown

Fired when the widget is shown.

```javascript
RocketChat(function() {
    this.onWidgetShown(function(data) {
        // do whatever you want
        console.log('chat widget shown');
    });
});
```

### onAgentStatusChange

Fired when the status of the current agent changes.

```javascript
RocketChat(function() {
    this.onAgentStatusChange(function(data) {
        // data is an object containing the following fields: name, username and status

        // do whatever you want
        console.log('The status of the agent has changed');
    });
});
```

### onServiceOffline

Fired when a visitor tries to start a new conversation and the Livechat service is offline.

```javascript
RocketChat(function() {
    this.onServiceOffline(function(data) {
        // do whatever you want
        console.log('The Livechat service is offline');
    });
});
```

## Change Log

| Version | Description                                                                                                                                            |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 6.7.0   | Added `setGuestMetadata` method.                                                                                                                       |
| 3.1.0   | Added `setAgent` and `initialize` methods. Also, improved the `setTheme` method adding more options to customize the widget                            |
| 3.0.0   | Added `onServiceOffline` callback                                                                                                                      |
| 2.2.0   | Added `maximizeWidget` and `minimizeWidget` methods.                                                                                                   |
| 1.3.0   | Added `onAssignAgent` and `onAgentStatusChange` methods.                                                                                               |
| 1.1.0   | Added `showWidget` and `hideWidget` methods along with `onWidgetHidden` and `onWidgetShown` events                                                     |
| 1.0.0   | Added `setLanguage` method                                                                                                                             |
| 0.66.0  | Added `setGuestToken`, `setGuestName`, `setGuestEmail` and `registerGuest` methods.                                                                    |
| 0.53.0  | Added callback events and the ability to pass a flag to `setCustomField` so the value passed does not get wrote if there is already an existing value. |
| 0.36.0  | Added `setTheme` method                                                                                                                                |
| 0.26.0  | Added `setCustomField` method                                                                                                                          |
