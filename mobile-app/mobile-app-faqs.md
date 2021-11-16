# Mobile App FAQs

## **Why I'm not receiving push notifications on mobile apps?**

First of all, make sure you understand our Push Notification workflow and the app should be receiving a push notification.If you're using a SaaS, make sure you have enough Push Notification quota.If you're self hosted, make sure your gateway is properly configured.

## **Do I need previous knowledge to build a white label app?**

Yes, you'll need intermediate iOS and Android experience in order to be able to build and upload your apps to the stores.

**Will **[**Rocket.Chat**](http://rocket.chat)** push notification gateway work on my whitelabel app?**

No, [Rocket.Chat](http://rocket.chat) gateway works only for [Rocket.Chat](http://rocket.chat) apps on the stores. You'll need to [configure push notification](https://developer.rocket.chat/mobile-app/mobile-app-white-labelling#push-notification) on your server.

## **Why is Bugsnag required to build my white label app?**

Every app should contain some level of error tracking so you can find issues happening and fix them. If you find any bugs on your app built from source, you can contribute back to the community or open a new issue on our [Github Repository](https://github.com/RocketChat/Rocket.Chat.ReactNative/) and we can fix them on an upcoming version of the app. A bug might be caused during the whitelabel process, so it's important to be aware of them. If you know the risks and still want to remove Bugsnag from your app, you can follow their [installation guide](https://docs.bugsnag.com/platforms/react-native/react-native/#installation-and-configuration), but undoing everything. Additionally, if you think we should remove the Bugsnag dependency from our project, let us know by [filing an issue](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues/new) and we're happy to discuss with you further!

## **"single-server" branch is outdated. When is it going to be updated?**

We always keep whitelabel up-to-date to the [Rocket.Chat](http://rocket.chat) apps on App Store and Google Play. Once a new version is released, we update it to match new content.
