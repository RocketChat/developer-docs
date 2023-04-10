# Analytics & Data Usage

## Crashlytics and Bugsnag

Both iOS and Android applications use Crashlytics and Bugsnag to send crash information. Both platforms collect crash information from mobile apps, transmit it, and store them securely on their servers for developer diagnosis. This transmitted data contains no users, channels, or groups information; it does not contain any message content. The collected content contains only anonymous application and system state information during the crash that can be helpful for diagnosis.

_These reports can be disabled on both iOS and Android if the user goes to the Settings screen and disables crash reports._

## Firebase Analytics

We use Firebase Analytics to report events of usage in the app for some actions, such as sending messages, reacting, changing the theme of the app, etc. This is also anonymous information and does not contain any private information from the user. This is only being used to understand what features are being used more and how they're being used.

_These reports can be disabled on both iOS and Android if the user goes to the Settings screen and disables crash reports._
