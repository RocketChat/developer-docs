# Analytics & Data Usage

## Crashlytics and Bugsnag

Both iOS and Android applications use Crashlytics and Bugsnag to send crash information. These platforms collect crash information from mobile apps, transmit it, and store them securely on their servers for developer diagnosis. The transmitted data contains no users, channels, or groups information and no message content. The collected content contains only anonymous application and system state information during the crash that can be helpful for diagnosis.

## Firebase Analytics

We use Firebase Analytics to report app usage events for some actions, such as sending messages, reacting, changing the theme of the app, etc. It is also anonymous and contains no private information from the user. It is only used to understand what features are used more and how they're used.



{% hint style="info" %}
Users can disable these reports on iOS and Android by disabling crash reports in the Settings screen.
{% endhint %}
