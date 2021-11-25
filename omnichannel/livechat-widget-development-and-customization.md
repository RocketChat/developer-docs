# Livechat Widget Development and Customization

## Development&#x20;

### Changing LiveChat Host.

One of the very first things to do while developing the LiveChat widget is to make sure it points directly to your running RocketChat server.

To select a different host for your local widget, navigate in the project directory to the  `/src/api.js` file.

```
const host = window.SERVER_URL
	|| queryString.parse(window.location.search).serverUrl
	|| (process.env.NODE_ENV === 'development' ? 'http://localhost:3000' : null);
```

You can modify to your server's URL.

```
const host = window.SERVER_URL
	|| queryString.parse(window.location.search).serverUrl
	|| (process.env.NODE_ENV === 'development' ? 'https://your.rocketserver.com' : null);
```

### Available CLI Commands

```
# install dependencies
yarn

# serve with hot reload at localhost:8080
yarn start

# build preact application to "build" folder
yarn dev

# build for production with minification
yarn build

# test the production build locally
yarn serve

# run tests with jest and preact-render-spy
yarn test

# run the storybook
yarn storybook

# before commit run
yarn i18n
```

## Customization

The Livechat widget can be fully customized using following our [**Storybook components**](https://rocketchat.github.io/Rocket.Chat.Livechat/)**.**

You can use the Livechat Widget API to extend functionalities.

{% content-ref url="../reference/api/livechat-api.md" %}
[livechat-api.md](../reference/api/livechat-api.md)
{% endcontent-ref %}
