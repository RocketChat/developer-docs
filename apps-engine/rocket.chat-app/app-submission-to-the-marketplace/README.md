# App Submission to the Marketplace

So, you just finished writing your first Rocket.Chat App, and you have successfully tested it locally which means you are ready to submit it to the Marketplace for others to use. This article will take you through the process, step-by-step.

{% hint style="info" %}
When you submit an App, there is a three-step process that takes place. In the first step, you submit the App to the Marketplace (explained below). Secondly, you will receive an email that asks for you to approve or reject the App submission (more on this later as well). Finally, after you approve the entry, then our staff will review it and determine whether it is to be approved published or not.
{% endhint %}

## Packaging the app

Currently the Rocket.Chat servers and Marketplace allow submission of zip files, these files can be created by running `rc-apps package` which packages your app and creates the zip file under `dist` folder.

## App Submission

To be able to submit an App to the Marketplace, the Publisher must have a Rocket.Chat [Cloud Account](https://cloud.rocket.chat/login) and register their [Publisher Account](https://marketplace.rocket.chat/publisher/register).

### Submission through CLI

To submit your App simply run:

`rc-apps submit`

![](<../../../.gitbook/assets/image (186) (1).png>)

{% hint style="info" %}
Submission through CLI just sends the App in a `draft` state. The Publisher must access the Portal to be able to submit the app.
{% endhint %}

### Submission through Publisher

To submit an app through the publisher:

1. Go to [https://marketplace.rocket.chat/publisher/register](https://marketplace.rocket.chat/publisher/register) (provided in the CLI)
2. Log in using your account

![](<../../../.gitbook/assets/image (55).png>)

Or Sign up for your publisher account,  as shown below:

![](<../../../.gitbook/assets/image (183).png>)

Your publisher developer account is created, as shown below:

![](<../../../.gitbook/assets/image (48).png>)

## To add a new app:

1. Click **New App**

![](<../../../.gitbook/assets/image (19).png>)

Following screen appears:&#x20;

![](<../../../.gitbook/assets/image (45).png>)

2\. Drag and drop your app package, as shown below:

![](<../../../.gitbook/assets/image (64).png>)

Click **Next** and set details of the app you're going to publish.

## **Set App details:**

1. Set your app's name under **App Name**.
2. &#x20;Use **Upload new app** button to upload and set a display picture for your app.&#x20;
3. Select a category for your app in **Categories** drop-down.&#x20;
4. Select a Language for your app in **Languages** drop-down.&#x20;

## Purchase Type:

In the following section we will guide you through different purchase types. You can choose the one that suits your needs.

![](<../../../.gitbook/assets/image (56) (1).png>)

{% hint style="info" %}
For a paid app its madatory to connect with [Stripe](https://stripe.com) account before submission.
{% endhint %}

{% hint style="info" %}
Your users are allowed to buy the app per workspace. If they have two workspaces and want to use the app on both, they need to buy the app separately.
{% endhint %}

### One-time Purchase:

Please use **One-time Purchase** when you want your app to have a one-off payment and your users  are allowed to use it forever after that payment. To set it:

1. Select One-time Purchase
2. Enter the price you want to set

![](<../../../.gitbook/assets/image (31).png>)

### Subscription:

When you want your app to be subscription-based, you can use **Subscription** purchase type. An example of this volume-based pricing is shown below:

1. Select **Subscription**
2. Click **Add pricing plan**

![](<../../../.gitbook/assets/image (11).png>)

**New Pricing Plan** pane appears:

3\. Select your subscription **Strategy** (Monthly/Yearly)&#x20;

4\. Mention the Price

5\. There are two types of subscribtion plans to to choose from: &#x20;

#### **5.1** Per Seat Subscription&#x20;

If you want your app to have a per seat subscribtion check mark **Per Seat** box.

{% hint style="info" %}
Per seat subscribtion allows your customers to pay per seat for the app rather than paying for a tier of users.
{% endhint %}

![](<../../../.gitbook/assets/image (3).png>)

#### **5.2** Tiers Subscription&#x20;



### Free:

You can make your app available to your customers free of cost,  as shown below;

![](<../../../.gitbook/assets/image (2).png>)

## App Info

Next you can set your app info:

* You can upload some images of your app, (Screenshots (1200x600 px), (max of 5 images))
* Set its description
* Mention privacy and data handling rules

as shown below:

![](<../../../.gitbook/assets/image (22).png>)

## Publish App

Hit **Publish Changes**, as shown below:

![](<../../../.gitbook/assets/image (40).png>)

Your app is published successfully, as shown below:

![](<../../../.gitbook/assets/image (15).png>)

## Process after successful submission:

After successful submission following events happen at Rocket.Chat side, that you should be aware of:

* Compiling
* Approvement
* Publishing

You can see the status of your app as **compiling**, as shown below:

![](<../../../.gitbook/assets/image (191).png>)

After we compile, you will be notified via email, as shown below:

![](<../../../.gitbook/assets/image (194).png>)

Then you get notified to review your app, as shown below:

![](<../../../.gitbook/assets/image (192) (1).png>)

You log in to your cloud account and **approve** it.

After your approval, rocket.chat reviews it, and you will be notified via email that your app is now **Published** (listed).
