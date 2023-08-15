# Mobile App

The Rocket.Chat Mobile App is built using React Native, allowing you to develop Android and iOS applications from a single codebase. Setting up the development environment requires you to download and install multiple dependencies.

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

{% hint style="warning" %}
Follow the[ official documentation](https://reactnative.dev/docs/environment-setup) to set up your React Native environment. Navigate to the `React Native CLI Quickstart` section, as we don't support Expo-managed flow.
{% endhint %}

## Set up the codebase

* Clone the [GitHub repository](https://github.com/RocketChat/Rocket.Chat.ReactNative) and install the required dependencies by running these commands:

```
git clone https://github.com/RocketChat/Rocket.Chat.ReactNative.git
cd Rocket.Chat.ReactNative
yarn
```

* Run the app by executing these commands:

**for **_**iOS**_**:**

```
npx pod-install
yarn ios
```

**for **_**Android**_:

```
yarn android
```

Now, the app is running on the simulator or your device.

#### Contributing

If you are yet to find a bug or want a new feature that hasn't been reported, see the [help wanted](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%91%8B+help+wanted%22) sections or the [good first issue](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues?q=is%3Aissue+is%3Aopen+label%3A%22%F0%9F%8D%AD+good+first+issue%22) labels. Triaging issues is a great way to contribute if you can't code.

{% hint style="info" %}
To learn more about Rocket.Chat contribution process, see [participate-in-rocket.chat-development](../../contribute-to-rocket.chat/modes-of-contribution/participate-in-rocket.chat-development/ "mention").
{% endhint %}

You have the option to share your ongoing work before completion by adding **\[WIP]** to your pull request (PR) title. This allows others to review your code and offer assistance if you encounter challenges while solving a problem.
