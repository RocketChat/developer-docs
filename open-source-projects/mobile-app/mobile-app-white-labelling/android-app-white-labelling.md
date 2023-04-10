# Android App White Labelling

## General setup

* Similarly to iOS, we have build flavors to generate our Official, Experimental and F-Droid versions of the app
  * `experimental` and `official` folders contain app icons and splash screens
  * `play` and `foss` folders contain necessary code to run the app with or without Google Play services, respectively
    * `foss` build doesn't contain push notifications implemented
  * `main` folder contains core implementations
  * `debug` folder contains code to run the app in debug mode
  * This doc is going to focus on building the Experimental app, so we're going to use `experimental`, `play` `debug`, and `main` folders

![](<../../../.gitbook/assets/image (177).png>)

* Set `APPLICATION_ID`, `VERSIONCODE` and `BugsnagAPIKey` on `./android/gradle.properties`
* Generate a [new image asset](https://developer.android.com/studio/write/image-asset-studio) for `ic_notification` and target `main`
* Generate a [new image asset](https://developer.android.com/studio/write/image-asset-studio) for `ic_launcher` and target `experimental`
* Splash screen is going to use the same asset as the `ic_launcher` and you can change the background on `splashBackground` as below

![](<../../../.gitbook/assets/image (180).png>)

* Change app name and share extension name on `./android/app/src/main/res/values/strings.xml`

![](<../../../.gitbook/assets/image (174).png>)

## Generate upload key

* This step will generate the keystore that is going to verify your app on Google Play
  * You can use this guide as a reference: [https://reactnative.dev/docs/signed-apk-android#generating-an-upload-key](https://reactnative.dev/docs/signed-apk-android#generating-an-upload-key)
* Execute the following on terminal
  * `cd android/app`
  * `keytool -genkeypair -v -keystore my-upload-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000`
* Credentials will be prompted

![](../../../.gitbook/assets/15.png)

* Set `KEYSTORE_PASSWORD` and `KEY_PASSWORD` on ./android/gradle.properties with the passwords you were prompted

## Generating Android app on Firebase

* Visit the project overview on [https://console.firebase.google.com](https://console.firebase.google.com)
* Click on the gear icon and then “Project settings”

![](https://lh6.googleusercontent.com/W9wKhlYZOFc\_f9G7CEpOM\_87qw\_8dvxE08nscN\_QIskcTW9ImOSqVckJewhp2j-f5wnClxkE8EaAszD7Z1rLFDbtfc56dXH-S\_aEou6HLwcEA\_rEDDIQTyEy4d1dtPwxXVxVu-JO)

* On “General” tab, click on “Add app” button under “Your apps” section and then “Android”

![](https://lh3.googleusercontent.com/SjEalr1zhiPne9Wm43vGiWQ1VtOXGownd0YYDWlEYa5hRpY69Z0L7BY7H07HZ4Q3o9KEAbJpCHi6fO\_qH1k0WyHqr4lfC3VL-eCH-as\_lN85UmEIL4iQ6RTcljHMqbJf1ElGsTB8)

![](https://lh5.googleusercontent.com/2DQKam8jGt20nIF1KbKZGU2UMJBwdVKOiLo0hIn3S3upZJytt3aHt6fzPT2sezotlYTKoqflRNRUdONQtXeAxC2Dbi00Dpf80aomGRQxjGmkOq62ubLoNTzxWoF9DWb4M3rlXWi-)

* Enter your bundle ID and then “Register app”

![](https://lh6.googleusercontent.com/t4\_xn2ud8KnPKDfQ4r2Hk7jo4bYs85ZQ8LmYFeFwD6tB3qt3a8U1l3x1HsFcDE0yRKe1PI8AXDD-4J-8QoQMarD7riUwO3hjF4YURBKOe8hlJZHRCvt1E49TxVVZSkPSAfKg7OFB)

* Download the config file and move it as instructed

![](https://lh5.googleusercontent.com/k7CjPaIbiBvkd3wY1Exl6FGZsmC5blK8pNW3fycI9NAVZ9rWwdVNHtSTV6EWHQFasep9tOf0k0nEE36khTIxgtTr4se2\_NM6lJmgeM20M5lhMPupoc0BjhouH7B7X3jnP5CvgMg6)

![](<../../../.gitbook/assets/image (33).png>)

## Running the app

* Execute the following on project terminal
  * `yarn`
  * `yarn android-whitelabel <YOURAPPID>`
  * For example, the app created on this document would use `yarn android-whitelabel chat.rocket.whitelabel`
* Note: this script uses `experimentalPlayDebug` build flavor. When you build your app on release mode, use `experimentalPlayRelease`
  * Refer to [https://developer.android.com/studio/build/build-variants](https://developer.android.com/studio/build/build-variants) for more info about how it works
