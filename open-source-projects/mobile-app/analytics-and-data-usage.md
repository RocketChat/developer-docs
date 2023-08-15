# Analytics & Data Usage

In the fast-paced world of mobile communication, where speed and efficiency are paramount, harnessing the power of data analysis becomes the cornerstone of delivering an exceptional user experience. Developing mobile apps for Rocket.Chat requires careful analysis and consideration of data usage to ensure a smooth user experience. Rocket.Chat Mobile apps can use a significant amount of data, especially if they are used to send and receive large files or images. It is important to be aware of the data usage implications of your app and to design it accordingly.

## Crashlytics and Bugsnag

Rocket.Chat utilizes [Crashlytics](https://firebase.google.com/products/crashlytics) and [Bugsnag](https://www.bugsnag.com/solutions/mobile/) for crash reporting in both iOS and Android apps. These tools collect crash information from mobile apps, transmit it, and store them securely on their servers for developer diagnosis. The transmitted data contains no users, channels, or group information and no message content. It contains only anonymous application and system state information during the crash that can be helpful for diagnosis. This data can be used to identify and fix bugs that are causing crashes.

## Firebase Analytics

Firebase Analytics is used to track app usage events in Rocket.Chat like sending messages or changing themes. It is also anonymous and contains no private information from the user. It is only used to understand what features are used more and how they're used. This data can be used to improve the performance and usability of your app and to make better decisions about its future development.

{% hint style="info" %}
Users can disable these reports on iOS and Android by disabling crash reports in the Settings screen.
{% endhint %}
