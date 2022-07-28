# iOS App White Labelling

## General setup

* Open [RocketChatRN.xcworkspace](https://github.com/RocketChat/Rocket.Chat.ReactNative/tree/single-server/ios/RocketChatRN.xcworkspace) on Xcode (13.0 or newer)
* On the General tab, select “RocketChatRN” and change Display Name, Bundle Identifier, Version and Build

{% hint style="info" %}
As explained in the [Important section](https://developer.rocket.chat/mobile-app/mobile-app-white-labelling#important), we have two targets and we're going to cover the default one on this doc, which is the Experimental app.
{% endhint %}

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.42.41.png)

* Select “ShareRocketChatRN” and change the same properties
  * `Display Name` and `Bundle Identifier` are different from the previous target
  * `Version` and `Build` must be the same on all targets

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.42.50.png)

* Select “NotificationService” and change the same properties
  * `Display Name` and `Bundle Identifier` are different from the previous target
  * `Version` and `Build` must be the same on all targets

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.42.59.png)

* On Signing and Capabilities, check “Automatically manage signing”, select your app group and add a keychain group

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.39.48.png)

* Select “ShareRocketChatRN”, check “Automatically manage signing”, select your app group and add the same keychain group

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.39.33.png)

* Select “NotificationService”, check “Automatically manage signing”, select your app group and add the same keychain group

![](../../.gitbook/assets/screen-shot-2020-10-05-at-16.39.58.png)

* Set the same app group on `RocketChatRN/Info.plist`, `ShareRocketChatRN/Info.plist` and `NotificationService/Info.plist`

![](https://lh5.googleusercontent.com/BEV\_JFzqUS3OX5mStoT1ParmsmQtRhtnHTGrBhzkHq-Lrf3rabjg1pnDlUqmEDaHXySmHzE-Iqtn07gL7FN6wGrbTAiLu3JFC5yN6qW1C3u3HnSqDQWZQ08hmp0jXhjplLeKmcyr)

![](https://lh3.googleusercontent.com/o3iotTRPf5V7C6PZiZ9SYwWR\_suvnW8mflVSABFaRaRzRuKm4SBRrbLiAVceStFpj7WWGs3xNJO\_2cqT7EeRxet9fQoX7MYuUWjLfOBhScEXt5HZVB1XEQxtYrH5Oh8juv1Iz0hu)

![](<../../.gitbook/assets/image (35) (1) (3) (3) (3) (3) (2).png>)

* Set the same keychain group on `RocketChatRN/Info.plist`, `ShareRocketChatRN/Info.plist` and `NotificationService/Info.plist`

![](<../../.gitbook/assets/image (36).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (37).png>)

* It needs to be the same on all entitlements

![](<../../.gitbook/assets/image (39).png>)

![](<../../.gitbook/assets/image (44).png>)

![](<../../.gitbook/assets/image (42).png>)

* Change the app icon on `Experimental.xcassets/App Icon`

![](<../../.gitbook/assets/image (178) (3) (3) (3) (3) (3) (2) (3).png>)

* Change the app splash screen on `Experimental.xcassets/Launch Screen Icon`

![](<../../.gitbook/assets/image (175).png>)

* Change the splash background colors on `Experimental.xcassets/splashBackgroundColor`

![](<../../.gitbook/assets/image (179).png>)

* Set your Bugsnag API key on `RocketChatRN/Info.plist`

![](../../.gitbook/assets/image.png)

## Generating iOS app on Firebase

* Visit the project overview on [https://console.firebase.google.com](https://console.firebase.google.com)
* Click on the gear icon and then “Project settings”

![](https://lh6.googleusercontent.com/W9wKhlYZOFc\_f9G7CEpOM\_87qw\_8dvxE08nscN\_QIskcTW9ImOSqVckJewhp2j-f5wnClxkE8EaAszD7Z1rLFDbtfc56dXH-S\_aEou6HLwcEA\_rEDDIQTyEy4d1dtPwxXVxVu-JO)

* On “General” tab, click on “iOS” button under “Your apps” section

![](https://lh3.googleusercontent.com/yWR4dImy-l6-B79Xtw1VR1bOOeKFFS05h9yh3dsulbv6pbr1dLljd0KgxNn3MpzInUZF6xtw\_KAOfYVZKXuqzVf-ybavOTtJ92tX-N\_h7QhHi6X0AA3qZuqsenUnDHNvnqwmTvpX)

* Enter your bundle ID and then “Register app”

![](https://lh6.googleusercontent.com/64SZsPUtnHS1xw3UPvG0Pxd4ljeJ4r42KQWqhrOn-aYQQMvqaH7hXH07T9aaWv\_ImTRnDMm0QQdst0hVnIFtAz6cd-I8Tr8K9YDpld6mcNYc6Q6-5nsRlXqQibdnJSBVrHjtXrzE)

* Download config file and move it as instructed

![](https://lh6.googleusercontent.com/aOiSAtt1YF-nsaZIHhKesYjdTzlsEN3T-mqZ2fvBvZJV95jl6LfBBjT0hS8ufaAyHytAdn-0yhjjkJ8kGLJ1RIZJvGYIpNtUon6\_WPaSA7GZ-yyDslpCKSDUtnYaK8E0l4Z4mR1O)

* Add it to all targets

![](<../../.gitbook/assets/image (43).png>)

## Running the app

* Execute the following on project terminal
  * `yarn`
  * `npx pod-install`
  * `yarn ios`

## Configuring the Apple Developer Portal

### Login to Apple Developer Portal

* Visit [https://developer.apple.com/account](https://developer.apple.com/account/resources/certificates/list)
* Enter your credentials
* Click on Certificates, Identifiers & Profiles

![](../../.gitbook/assets/23.png)

### Creating an App Identifier

* Visit [https://developer.apple.com/account/resources/identifiers/list](https://developer.apple.com/account/resources/identifiers/list)
* Click to add Identifier
* Select App IDs and Continue

![](https://lh5.googleusercontent.com/fBgW0bm87EUIxW6yJwWIA3qE96RRXXvesYyrGuzQ63OuXpJmPsEtYgnFFaVsuR0\_ho3xorv1rE\_UuxNlhHj9ewYyk57fENVQykRtn-Zpm8rKmHIBi9r9lmAsNH6Fhxx8wCZfOq4b)

* Add description and Bundle ID

![](https://lh4.googleusercontent.com/JhzGmNHMLFB8k16GjrAFa0z5kP7R2gMr0qvs\_k9hxK4g3JRwz7jpEkFuN3yzQ4mwd380zguniK1pGvfbsah0i2voB1xpFSxTZzJ3\_Ap16L0z8QCI3PYSxPHXfiY4PVfQnUaxVENG)

* On Capabilities, select App Groups and Push notifications
* Click “Continue” and then “Register”

### Creating an App Identifier for our Share Extension

* Share Extension is a version of the app that opens when you share data from another app to Rocket.Chat. For example, share a photo from the gallery.
* Visit [https://developer.apple.com/account/resources/identifiers/list](https://developer.apple.com/account/resources/identifiers/list)
* Click to add Identifier
* Select App IDs and Continue

![](https://lh5.googleusercontent.com/fBgW0bm87EUIxW6yJwWIA3qE96RRXXvesYyrGuzQ63OuXpJmPsEtYgnFFaVsuR0\_ho3xorv1rE\_UuxNlhHj9ewYyk57fENVQykRtn-Zpm8rKmHIBi9r9lmAsNH6Fhxx8wCZfOq4b)

* Add description and Bundle ID

![](https://lh5.googleusercontent.com/KJWk8QgL8lVOczT4DMaTrPvZrLsqwyJSguCuH9\_\_NPDLOx\_s0CojrUE5COtAU\_frKHVHbDmoyRIrUmzMB9m28g9g4v7E87365bPZuCULfyHgGLCnLJryhbfXJA9XzLoQ0TXIFCSP)

* This time, select only App Groups under Capabilities
* Click “Continue” and then “Register”

### Create an App Identifier for our Notification Service

![](<../../.gitbook/assets/image (38).png>)

### Creating an App Group

* Visit [https://developer.apple.com/account/resources/identifiers/list](https://developer.apple.com/account/resources/identifiers/list)
* Click to add Identifier
* Select App Groups and Continue

![](https://lh6.googleusercontent.com/9HIEqXPESh2ovfCnnGsq40A9cvrUYdrRZGMnP9j71Ssxoz5xBfdkoaD-D7Gpds6RJz3psb-eze8kaKUfrM6IZdK1e\_9Zx8jKAI02\_mD74JGhCEA4exVI6Dp9IJImI5pdFQvfn4Kh)

* Enter a description and an Identifier

![](https://lh6.googleusercontent.com/0xhE6ekIILrExeeIAd8logt77SDiGX26zZ7yGKI8yZCjcDRTTjtPVBO2tBAklCJvX03PqcB71eTCPytIwtDVx7TGCDX81eTc1Vy9QdQNKkDDTG4sGStQw52GDbZr5zpr9TF\_7Mbh)

* Click “Continue” and then “Register”

### Applying App Group

* Visit [https://developer.apple.com/account/resources/identifiers/list](https://developer.apple.com/account/resources/identifiers/list)
* Click on the first identifier you created
* On “App Groups”, click “Configure”
* Select the App Group you created and click “Continue”
* Click “Save”
* Repeat these steps for the second identifier you created for the Share Extension and NotificationService

### Creating Push Notifications certificates

* Visit [https://developer.apple.com/account/resources/identifiers/list](https://developer.apple.com/account/resources/identifiers/list)
* Click on the first identifier you created
* On “Push Notifications”, click “Configure”

![](../../.gitbook/assets/30.png)

#### Development SSL Certificate

* On “Development SSL Certificate”, click “Create Certificate”
* Follow Apple’s tutorial to generate a Certificate Signing Request: [https://help.apple.com/developer-account/#/devbfa00fef7](https://help.apple.com/developer-account/#/devbfa00fef7)
* Select the certificate you created and click “Continue”

![](https://lh4.googleusercontent.com/pv8BFR0k34C4G72y1-KxqgHmKbTMN59gCI2p2NbxevJNG7TtW2G3fpPhYjds-tSnbLCEdB9xj6N5P4XCxtJwaKAJSP2diMoP8jp3AN-pdIWlYfcaIDsVabzq1qvQ8aUBcAzOWPxn)

* Download the certificate and install it on your machine (follow the instructions on the screen)

![](https://lh6.googleusercontent.com/bxWWaArRsUZ3XrQ3s5ldGTwuLjwc9BhqvEOODJWTe8ep5rKdfqCVMWeZF0ZBg0oWS69Uwr\_0WBApU9oLMZdqiG8G\_DX7UEqqsjE\_OAsjPyIxXKSNMpjFGJgVf6H7GUUzArkmCBAP)

* After installing it, “Keychain Access” should have opened automatically on your Mac
* Export the certificate to generate a .p12 file

![](https://lh4.googleusercontent.com/QXJ01OEmH9V67hw\_pphtNyuVL25iLu3H1335ZBt6L8yvQQZU4NkllRYcBFSushRZk1IzY1kC0J62POYWg0XoeSmdolQ2d-g4NnD2Y4JlEdoVQXF6RRoRNoBZuRZBWAfsqZy334LN)

* For simplicity, save it in the same folder of your CSR and .cer. You’ll need it later.

#### Production SSL Certificate

* On “Production SSL Certificate” click “Create Certificate”
* Follow Apple’s tutorial to generate a Certificate Signing Request: [https://help.apple.com/developer-account/#/devbfa00fef7](https://help.apple.com/developer-account/#/devbfa00fef7)
* Select the certificate you created and click “Continue”

![](https://lh5.googleusercontent.com/bdlcvworJPKW1iUzy3G\_wAASYOILEpCWDkI7BRdl7uk\_JD0FqK7n-\_M7rOY-Nd194IkU0KbaGjRRR2Zxf93xYyxUqW129t7lDaZErzqQzhYriYVxYn2qPPFjA3mcnN6YCM6zOqcu)

* Download the certificate and install it on your machine (follow the instructions on the screen)

![](https://lh3.googleusercontent.com/qEWMSoSAlC8ETDC3sVKOsbNo5bM34ZbSrKRavq\_XP\_b2KdsUaC1H8NCUfE-cAF3k-JAxEk4pyWk6S-NEoPCKcTA56IwcETJiMgQK2sRvpuF\_kzaWBrDTEF1y0Lz6ewzUDbgfj6I1)

* After installing it, “Keychain Access” should have opened automatically on your mac
* Export the certificate to generate a .p12 file

![](https://lh3.googleusercontent.com/WCLBhK5CneauBC7xQH3atoiHS3HE9YvJ7IaC5hCdGQVh3sx8CtF2u4vjcBc1e-LVl0zWXTwhrXzct8HcGLAk6D3A7eZHYiVHTzsAGdMNZ2jGADKi0jwXFiYoVhOyytvfiRqm4HuV)

* For simplicity, save it in the same folder of your CSR and .cer. You’ll need it later.
