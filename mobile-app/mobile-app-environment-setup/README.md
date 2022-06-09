# Mobile App Environment Setup

The Rocket.Chat mobile app is developed with React Native, helping us create both Android and iOS applications from a single codebase.

Setting up the development environment requires you to download and install multiple dependencies. You will need an active internet connection throughout the process.

## Requirements

You are required to have the following installed already on your machine before starting.&#x20;

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [Yarn](http://yarnpkg.com/) (recommended instead of npm)
* macOS with `XCode Command Line Tools` is needed to run the iOS version
* Android Studio is needed to run the Android version

Additionally, refer to [React Native environment set up](https://reactnative.dev/docs/environment-setup) to make sure everything is up and running. Follow the `React Native CLI Quickstart` section as we don't support Expo managed flow.

## Get the Code

### How to run

Clone repository and install dependencies:

```
git clone git@github.com:RocketChat/Rocket.Chat.ReactNative.git
cd Rocket.Chat.ReactNative
yarn
```

Run the app:

```
npx pod-install
yarn ios
```

or

```
yarn android
```

At this point, the app should be running on the simulator or on your device!

{% hint style="warning" %}
_npm won't work on this project._
{% endhint %}

{% content-ref url="supporting-ssl-for-development-on-rocket.chat.md" %}
[supporting-ssl-for-development-on-rocket.chat.md](supporting-ssl-for-development-on-rocket.chat.md)
{% endcontent-ref %}

{% content-ref url="analytics-and-data-usage.md" %}
[analytics-and-data-usage.md](analytics-and-data-usage.md)
{% endcontent-ref %}

## Contributing

### Issues needing help

If you didn't find a bug or want a new feature not already reported check out the [help wanted](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%91%8B+help+wanted%22) or the [good first issue](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%8D%AD+good+first+issue%22) labels.

Or if you can't help coding, triaging issues is a **great** way of helping.

### Pull request

As soon as your changes are ready, you can open a Pull Request.

The title of your PR should be descriptive, including either \[NEW], \[IMPROVEMENT], or \[FIX] at the beginning, e.g. \[FIX] App crashing on startup.

You may share working results prior to finishing, please include \[WIP] in the title. This way anyone can look at your code: you can ask for help within the PR if you don't know how to solve a problem.

Your PR is automatically inspected by various tools, check their response, and try to improve your code accordingly. Requests that fail to build or have the wrong coding style won't be merged.
