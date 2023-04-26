# Livechat Widget Development and Customization

## Changing LiveChat Host

One of the initial steps in LiveChat widget development is to ensure that it points directly to the running RocketChat server.

To select a different host for your local widget, navigate to `/src/api.js` file in the project directory.

It contains this code snippet:

```
const host = window.SERVER_URL
	|| queryString.parse(window.location.search).serverUrl
	|| (process.env.NODE_ENV === 'development' ? 'http://localhost:3000' : null);
```

You can modify your server's URL  in that code snippet like this:

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

The LiveChat widget can be fully customized using our [**Storybook components**](https://rocketchat.github.io/Rocket.Chat.Livechat/)**.** You can use the [**LiveChat Widget API**](../reference/api/livechat-api.md) to extend functionalities.
