# App Submission to the Marketplace

You have finished creating your first Rocket.Chat App, and successfully tested it locally. Now, you are ready to submit your App to the Marketplace for others to explore.&#x20;

This step-by-step guide will take you through the whole process of application submission.

## Package the app

Before submitting your app, you need to package it.  Currently the Rocket.Chat Servers and Marketplace allow submission of zip files, these files can be created by running the command `rc-apps package` in your Apps' directory. This will package your app and create a zip file under the `dist` folder. &#x20;

## App Submission

In this quickstart, you’ll learn how to submit your app to Rocket.Chat with two methods.

* App Submission through CLI

### App Submission through CLI

Submission through CLI sends the App in a `draft` state. The publisher must access the portal to be able to submit the app.

### Getting Started

To install a package

```
npm install -g @rocket.chat/apps-cli
```

### To develop Rocket.Chat app

#### Logging inside an app

Due to limitations of NodeJS's `vm` package we have had to implement a custom logger class. To make usage of this, you can use `this.getLogger()` and then do the normal `console` style logging.

#### `rc-apps create`

The development tools provide a command to quickly scaffold a new Rocket.Chat App, simply run `rc-apps create` and a new folder will be created inside the current working directory with a basic App which does nothing but will compile and be packaged in the `dist` folder.

#### App description

The app description file, named `app.json`, contains basic information about the app. You can check the [app-schema.json](https://github.com/RocketChat/Rocket.Chat.Apps-engine/blob/master/src/definition/app-schema.json) file for all the detailed information and fields allowed in the app description file, the basic structure is similar to this:

```
{
    "id": "5cb9a329-0613-4d39-b20f-cc2cc9175df5",
    "name": "App Name",
    "nameSlug": "app-name",
    "version": "0.0.1",
    "requiredApiVersion": "^1.4.0",
    "description": "App which provides something very useful for Rocket.Chat users.",
    "author": {
        "name": "Author Name <author@email.com>",
        "support": "Support Url or Email"
    },
    "classFile": "main.ts",
    "iconFile": "beautiful-app-icon.jpg"
}
```

#### Extending the App class

The basic creation of an App is based on extending the `App` class from the Rocket.Chat Apps _definition_ library. Your class also has to implement the constructor and optionally the `initialize` function, for more details on those check the [App definition documentation](https://rocketchat.github.io/Rocket.Chat.Apps-engine/classes/app.html).

```
import {
    IAppAccessors,
    IConfigurationExtend,
    IEnvironmentRead,
    ILogger,
} from '@rocket.chat/apps-engine/definition/accessors';
import { App } from '@rocket.chat/apps-engine/definition/App';
import { IAppInfo } from '@rocket.chat/apps-engine/definition/metadata';

export class TodoListApp extends App {
    constructor(info: IAppInfo, logger: ILogger, accessors: IAppAccessors) {
        super(info, logger, accessors);
    }

    public async initialize(configurationExtend: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void> {
        await this.extendConfiguration(configurationExtend, environmentRead);
        this.getLogger().log('Hello world from my app');
    }
}
```

#### To upload the app

For uploading the app you need to add to the required parameters in the .rcappsconfig already created in the apps directory. It accepts two types of objects:-

1. Upload using username, password

```
{
    url: string;
    username: string;
    password: string;
}
```

1. Upload using personal access token and userId

```
{
    url: string;
    userId: string;
    token: string;
}
```

#### To enable autocomplete for commands

To enable autocomplete for the apps cli use the command `rc-apps autocomplete <your-shell-type>` with the shell type as zsh or bash as the supported types. This would provide a step by step instruction to enable shell completion in your preferred shell.

### App Submission through Publisher

To submit an app to the marketplace, the publisher must have a Rocket.Chat [Cloud Account](https://cloud.rocket.chat/login) and register their publisher account.

**Create a Rocket.Chat Cloud account**

* Go to [https://cloud.rocket.chat/register](https://cloud.rocket.chat/register) to create your Rocket.Chat Cloud account.
* Enter your name, email address, and password.
* Make sure to accept the Rocket.Chat [Terms and Conditions ](https://docs.rocket.chat/legal/terms)and [Privacy Policy](https://docs.rocket.chat/legal/privacy).
* Click **Next.** You are notified that an email has been sent with the confirmation link to sign in to your Cloud account.
* Next, go to your inbox and confirm your email address by clicking on the link we sent; your cloud account has been created and is ready to use.&#x20;

**To submit an app through the publisher:**

1. Log in using your [cloud account](https://cloud.rocket.chat/login).

![Cloud Login](<../../.gitbook/assets/cloud login.png>)

Or sign up for your publisher account, as shown below:

![Publisher Registration](../../.gitbook/assets/PublisherAccountRegistration.png)

Your publisher developer account is created, as shown below:

![Publisher Profile](<../../.gitbook/assets/Publisher Profile.png>)

## Add your app

Click **New App.** The following screen appears with the following four tabs: **Upload, Details, Pricing, Screenshots,** and **Submission**

### **Upload**

* Drag and drop your app package or browse your app package .zip file and click **Next**.

![Upload App](<../../.gitbook/assets/publish a new app-Upload.png>)

Next , &#x20;

### **Details**

Click **Publish Changes**, as shown below:

Your app is published successfully, as shown below:

* Set your app's name under **App Name**.
* Use the **Upload new app** button to upload and set a display picture for your app.
* Select a category for your app in the **Categories** drop-down.
* Select a Language for your app in the **Languages** drop-down.

### **Pricing** &#x20;

Pricing Type - You can define how you can purchase type.

#### Purchase Type

We support the following purchase types:

* a
* b
* c

You can choose how you plan to distribute your app:

Click  purchase type  and select the plan you want to use.

In the following section we will guide you through different purchase types. You can choose the one that suits your needs.

{% hint style="info" %}
* For a paid app it is mandatory to connect with [Stripe](https://stripe.com/) account before submission.
* Your users are allowed to buy the app per workspace. If they have two workspaces and want to use the app on both, they need to buy the app separately.
{% endhint %}

#### One-time Purchase:

Please use **One-time Purchase** when you want your app to have a one-off payment and your users are allowed to use it forever after that payment.&#x20;

1. Select **One-time Purchase.**
2. Enter the price you want to set.

#### Subscription:

When you want your app to be subscription-based, you can use the **Subscription** purchase type. An example of this volume-based pricing is shown below:

1. Select **Subscription.**
2. Click **Add pricing plan.** A **New Pricing Plan** pane appears:

3\. Select your S**ubscription** **Strategy** (Monthly/Yearly)

4\. Mention the Price

5\. You have two types of subscription plans to choose from:&#x20;

#### Free

You can make your app available to your customers free of cost, as shown below;

![](<../../.gitbook/assets/image (2).png>)

* Price (USD) -

### **Screenshots**

Enter your details as prompted.

App Info -

Screenshots:

Description:

Privacy Policy Summary: You need to provide your app users with a brief summary of the privacy and data handling policies for this app.

Next, you can set your app information:

* You can upload some images of your app, (Screenshots (1200x600 px), (max of 5 images))
* Set its description
* Mention privacy and data handling rules

as shown below:

### **Submission**

Your app is almost ready to submit for review. Once you click Submit for Review, Rocket.Chat will review your code and reach you back via email as soon as possible. ****&#x20;

You can upload or drag and drop your app package, as shown below:

3\. Click **Next** and add the information of the app you're going to publish to the users.

## Process after the successful App submission:

After the successful submission following events will happen at Rocket.Chat side, that you should be aware of:

* Compiling
* Approvement
* Publishing

You can see the status of your app as **compiling**, as shown below:

After we compile, you will be notified via email, as shown below:

Then you get notified to review your app, as shown below:

You log in to your cloud account and **approve** it.

After your approval, Rocket.Chat reviews it, and you will be notified via email that your app is now **Published** (listed).
