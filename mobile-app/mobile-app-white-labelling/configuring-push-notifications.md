# Configuring Push Notifications

Without using a [Rocket.Chat SAAS](https://docs.rocket.chat/rocket.chat-saas) to manage your workspace, you can manually configure push notifications to your customized App build.

This will give the ability for your workspace users using mobile devices to receive push notifications on their devices. This guide shows how to achieve that.

## Configuring gateway

* In your Rocket.Chat workspace, go to **Administration** > **Settings** > **Push**
* Disable **Gateway** and hit **Save changes**

![](../../.gitbook/assets/21.png)

* Also disable **Production** if you’re trying in debug mode
* Expand “Credentials and Keys” section

## Configuring Android

* Go to Cloud Messaging on Firebase settings
* Copy “Server Key” token from Firebase into “GCM API Key”
* Copy “Sender ID” into “GCM Project Number”

![](../../.gitbook/assets/22.png)

## Configuring iOS

* Make sure you’ve done “Creating Push Notifications certificates” first
* In your terminal, go to the folder which contains your push files (CSR, .cer, .p12).

#### Generating PEM files (Development)

* Execute
  * `openssl x509 -in aps_development.cer -inform der -out DevPushCert.pem`
  * `openssl pkcs12 -nocerts -out DevPushKey.pem -in yourP12File.p12`
* You **must** set a password for your PEM file

#### Generating PEM files (Production)

* Execute
  * `openssl x509 -in aps.cer -inform der -out PushCert.pem`
  * `openssl pkcs12 -nocerts -out PushKey.pem -in yourP12File.p12`
* You **must** set a password for your PEM file

#### Copying PEM files to Rocket.Chat

* Copy the contents of your development PEM files and password into APN Dev Key, APN Dev Cert, and APN Dev Passphrase
* Copy the contents of your production PEM files and password into APN Key, APN Cert, and APN Passphrase
* You can use `cat` on the terminal to get the content of your PEM files
  * `cat PushKey.pem`
* Save and restart your server
* Log into the server as the same user on your mobile device and close it (it won’t receive push notification if it’s open)
* Open Push settings on admin from desktop and click “Send a test push to my user”

## Notification Workflow

{% embed url="https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC" %}
Page Embed from Whimsical: [https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC](https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC)
{% endembed %}

{% hint style="info" %}
You can find more information on push notifications configuration in our [admin guide.](https://docs.rocket.chat/guides/mobile-guides/push-notifications)
{% endhint %}
