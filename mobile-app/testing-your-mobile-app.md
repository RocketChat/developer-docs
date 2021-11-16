# Testing your Mobile App

It's always important to ensure everything is working properly and that's why tests are great. We have unit and e2e tests on this project.

### How to inspect the app

We use [Reactotron](https://github.com/infinitered/reactotron) to inspect logs, redux state, redux-sagas, HTTP requests, etc.

### Unit tests

We use [Jest](https://jestjs.io) and [Storybook](https://storybook.js.org) on our tests.

### **Storybook**

Storybook is a tool for developing UI Components and has some plugins to make Jest generate snapshots of them.

[On the root of the project](https://github.com/RocketChat/Rocket.Chat.ReactNative/blob/develop/index.js#L24), comment everything leaving only the last import to Storybook left and refresh your project. You'll see some tests like this:

[![](https://user-images.githubusercontent.com/804994/89677725-56393200-d8c4-11ea-84b0-213be1d24e98.png)](https://user-images.githubusercontent.com/804994/89677725-56393200-d8c4-11ea-84b0-213be1d24e98.png)

### **Jest**

We use Jest for our unit tests and to generate Storybook snapshots. We have a pre-commit hook enforcing preventing commits that breaks any test.

To check for test issues on your code, run this on your terminal:

```
yarn test
```

### E2E tests

We use [Detox](https://github.com/wix/Detox) framework to end-to-end test our app and ensure everything is working properly.

[Follow this documentation to learn how to run it](https://github.com/RocketChat/Rocket.Chat.ReactNative/blob/develop/e2e).

### Code style

We use [ESLint](https://eslint.org) to enforce code style and best practices. We have a pre-commit hook enforcing commits to follow our lint rules.

To check for lint issues on your code, run this on your terminal:

```
yarn lint
```

### Code formatting

We use [Prettier](https://prettier.io) to format the code style in our project. We have a pre-commit hook enforcing commits to follow our style guides.

To fix your code formatting issues, run this on your terminal:

```
yarn prettier
```

[Check this link](https://prettier.io/docs/en/editors.html) to see how to integrate Prettier with your preferred code editor, and run Prettier when save your file for example.
