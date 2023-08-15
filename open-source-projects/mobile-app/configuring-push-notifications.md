# Configuring Push Notifications

You can manually configure push notifications to your customized App build without using Rocket.Chat Saas to manage your workspace. It allows your workspace users using mobile devices to receive push notifications on their devices. This guide shows how to achieve that.

## Configuring Gateway

* Navigate to **Administration > Workspace > Settings** > **Push** on your workspace.
* Disable **Gateway** and click **Save changes.**
* Disable **Production** if you’re trying in debug mode.

## Configuring Android

* Navigate to the **Cloud Messaging** tab on the Firebase project.
* Copy the **Server Key** token from Firebase to the **GCM API Key** field in your workspace **Push > Certificates and Keys** settings.
* Copy the **Sender ID** from Firebase to **GCM Project Number** in your workspace **Push > Certificates and Keys** settings.

## Configuring iOS

* Ensure you have done "**Creating Push Notifications certificates**”.
* In your terminal, go to the folder which contains your push files (CSR, .cer, .p12).

#### Generating PEM files (Development)

To generate PEM files for a development environment,

* Run the following commands:

<pre><code>openssl x509 -in aps_development.cer -inform der -out DevPushCert.pem
<strong>
</strong><strong>openssl pkcs12 -nocerts -out DevPushKey.pem -in yourP12File.p12
</strong></code></pre>

* You **must** set a password for your PEM file.

#### Generating PEM files (Production)

To generate PEM files for a production environment,

* Run the following commands::

```
openssl x509 -in aps.cer -inform der -out PushCert.pem

openssl pkcs12 -nocerts -out PushKey.pem -in yourP12File.p12
```

* You **must** set a password for your PEM file

#### Copying PEM files to Rocket.Chat

* Copy the contents of your development PEM files and password into **APN Dev Key**, **APN Dev Cer**t, and **APN Dev Passphras**e on your **Push > Certificates and Keys** workspace settings.
* Copy the contents of your production PEM files and password into **APN Key, APN Cert, and APN Passphrase** on your  **Push > Certificates and Keys .**
* Get the content of your PEM files using `cat` by running this command:

```
cat PushKey.pem
```

* Save and restart your server.
* Log into the server as the same user on your mobile device and close it (it won’t receive push notification if it’s open).
* Navigate to  **Administration > Workspace > Settings** > **Push** and click on  the **Send a test push to my user** button**.**

## Notification Workflow

{% embed url="https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC" %}
Page Embed from Whimsical: [https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC](https://whimsical.com/notification-workflow-PRwN4MWNsxSwqHjHXaPUuC)
{% endembed %}

{% hint style="info" %}
You can find more information on push notifications configuration in our [admin guide](https://docs.rocket.chat/use-rocket.chat/rocket.chat-mobile/push-notifications).
{% endhint %}
