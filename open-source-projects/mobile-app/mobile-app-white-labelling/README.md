# Mobile App White Labelling

You can rebrand Rocket.Chat Mobile Apps to suit your style guide. You can customize the App Icons, Splash Screens, App Name, and Colors for your mobile app.

## Requirements

To customize your mobile apps, here are some essential requirements:

* Intermediate knowledge of Android/iOS development and basic Javascript knowledge.
* The repo contains targets/build flavors to build our **experimental** and **official** apps. Both apps are equal but released at a different paces in the stores.
* The experimental folder contains the assets for the non-official app. If you see it, avoid worrying about breaking anything.

## Set up the GitHub Repository

* Ensure you have both iOS and Google developer accounts and the respective development environments working.
* Follow the [Getting Started with ReactNative](https://reactnative.dev/docs/getting-started) guide.
* Clone the Rocket.Chat [ReactNative GitHub Repo](https://github.com/RocketChat/Rocket.Chat.ReactNative).&#x20;
* Checkout to the `single-server` branch.

{% hint style="info" %}
You can clone the single-server branch directly by  running this command:

`git clone -b single-server` [`https://github.com/RocketChat/Rocket.Chat.ReactNative`](https://github.com/RocketChat/Rocket.Chat.ReactNative)
{% endhint %}

## General

* Create an account on [Bugsnag](https://www.bugsnag.com/).
* Set `server`, `appGroup`, and `appStoreId` in the [app.json](https://github.com/RocketChat/Rocket.Chat.ReactNative/blob/single-server/app.json#L5) file.

{% hint style="info" %}
`appGroup` must be the same App Group created for the iOS app
{% endhint %}

* Change app colors in the [colors.ts](https://github.com/RocketChat/Rocket.Chat.ReactNative/blob/develop/app/lib/constants/colors.ts) file.

## Set up Firebase

### Creating a project Google Cloud Platform (GCP)

* Sign in to [Google Console](https://console.cloud.google.com/home/dashboard).
* Navigate to **New Project**.
* Fill in the required project details and click **Create.**
* You are redirected to the newly created project page.

### Creating a new Firebase project

* Sign in to [Firebase](https://console.firebase.google.com/).
* Click **Create a Project.**
* Select the [project you created in GCP](./#creating-a-project-google-cloud-platform-gcp).
* Follow the setup prompts and click "Create".

{% content-ref url="../../../mobile-app/mobile-app-white-labelling/ios-app-white-labelling.md" %}
[ios-app-white-labelling.md](../../../mobile-app/mobile-app-white-labelling/ios-app-white-labelling.md)
{% endcontent-ref %}

{% content-ref url="android-app-white-labelling.md" %}
[android-app-white-labelling.md](android-app-white-labelling.md)
{% endcontent-ref %}

{% content-ref url="configuring-push-notifications.md" %}
[configuring-push-notifications.md](configuring-push-notifications.md)
{% endcontent-ref %}
