# Mobile App

The Rocket.Chat Mobile App is built using React Native, allowing us to develop Android and iOS applications from a single codebase. Setting up the development environment requires you to download and install multiple dependencies.&#x20;

{% hint style="warning" %}
Please maintain an active internet connection throughout the installation process.
{% endhint %}

## Requirements

Before setting up, confirm that these tools are installed and running correctly on your device:

* [Git](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org)
* [Yarn](http://yarnpkg.com/) (recommended instead of npm)
* macOS with `XCode Command Line Tools` to run the iOS version,
* Android Studio to run the Android version.

{% hint style="info" %}
Follow the[ official documentation](https://reactnative.dev/docs/environment-setup) to set up your React Native environment. Navigate to the `React Native CLI Quickstart` section, as we don't support Expo-managed flow.
{% endhint %}

## Set up the codebase&#x20;

* Clone the [GitHub repository](https://github.com/RocketChat/Rocket.Chat.ReactNative) and install the dependencies by running these commands:

```
git clone git@github.com:RocketChat/Rocket.Chat.ReactNative.git
cd Rocket.Chat.ReactNative
yarn
```

* Run the app

for _iOs_:

```
npx pod-install
yarn ios
```

or, for _android_:

```
yarn android
```

Now, the app is running on the simulator or your device.

## Contributing

If you are yet to find a bug or want a new feature that hasn't been reported, see the [help wanted](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%91%8B+help+wanted%22) sections or the [good first issue](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%8D%AD+good+first+issue%22) labels. Triaging issues is a great way to contribute if you can't code.&#x20;

You can follow[ the guidelines](../../contribute-to-rocket.chat/ways-to-contribute/developing/development-workflow.md#creating-a-pull-request) to open a pull request when your changes are ready. You can also share working results before finishing. Including \[WIP] in the title. This way, anyone can look at your code: you can ask for help within the PR if you need help solving a problem.

Various tools automatically inspect your PR check their response, and try to improve your code accordingly. Requests that fail to build or have the wrong coding style won't be merged.
