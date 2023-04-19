# Testing your Mobile App

Tests are essential to ensure everything in the mobile app works properly. This project has **unit tests** and **e2e tests**.

## How to inspect the app

[Reactotron](https://github.com/infinitered/reactotron) is used to inspect logs, redux state, redux-sagas, HTTP requests, etc.

## Unit tests

For unit tests, we use [Jest](https://jestjs.io/) and [Storybook](https://storybook.js.org/).

### **Storybook**

Storybook is a tool for developing UI Components with some plugins to make Jest generate snapshots. [On the root of the project](https://github.com/RocketChat/Rocket.Chat.ReactNative/blob/develop/index.js#L24), comment everything leaving only the last import to Storybook. Then, refresh your project. You'll see some tests like this:

[![](https://user-images.githubusercontent.com/804994/89677725-56393200-d8c4-11ea-84b0-213be1d24e98.png)](https://user-images.githubusercontent.com/804994/89677725-56393200-d8c4-11ea-84b0-213be1d24e98.png)

### **Jest**

We use Jest for unit tests and to generate Storybook snapshots. There is a pre-commit hook to prevent commits that breaks any test.

To check for test issues on your code, run this command:

```
yarn test
```

## E2E tests

[Detox](https://github.com/wix/Detox) framework tests our app end-to-end and ensures everything works properly.

{% hint style="info" %}
To run the test, see the [e2e documentation](https://github.com/RocketChat/Rocket.Chat.ReactNative/tree/develop/e2e).
{% endhint %}

## Code style

[ESLint](https://eslint.org/) is used to enforce code style and best practices. There is a pre-commit hook enforcing commits to follow our lint rules.

To check for lint issues on your code, run this command:

```
yarn lint
```

## Code formatting

[Prettier](https://prettier.io/) is used to format the code style in our project. There is a  pre-commit hook enforcing the commits to follow our style guides.

To fix your code formatting issues, run this on your terminal:

```
yarn prettier-lint
```

{% hint style="info" %}
To integrate Prettier with your preferred code editor, see the [official documentation](https://prettier.io/docs/en/editors.html).
{% endhint %}
