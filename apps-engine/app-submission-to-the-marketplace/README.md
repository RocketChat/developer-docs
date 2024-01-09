# App Submission to the Marketplace

Now you have finished [creating your Rocket.Chat app](../getting-started/creating-an-app.md), and successfully tested it locally. Now, you are ready to submit your app to the marketplace for users to explore.

## Prerequisites

There are two ways to begin the process of submitting your app, via the [Apps-Engine CLI](../getting-started/rocket.chat-app-engine-cli.md) and via the [Marketplace Publisher portal](https://marketplace.rocket.chat/publisher/register). For both these methods, you must have a Marketplace Publisher portal account and a [Rocket.Chat Cloud account](https://cloud.rocket.chat/login).

### **Create a Rocket.Chat cloud account**

1. Go to [https://cloud.rocket.chat/register](https://cloud.rocket.chat/register) to create your Rocket.Chat Cloud account.
2. Enter your name, email address, and password.
3. Make sure to accept the Rocket.Chat [Terms and Conditions ](https://docs.rocket.chat/legal/terms)and [Privacy Policy](https://docs.rocket.chat/legal/privacy).
4. Click **Next.** You are notified that an email has been sent with the confirmation link to sign in to your cloud console.
5. Next, go to your inbox and confirm your email address by clicking the link we sent.&#x20;

Your cloud account has been created and is ready to use!

### **Create a Publisher account**

Go to [https://marketplace.rocket.chat/publisher/register](https://marketplace.rocket.chat/publisher/register) to sign up for your Publisher account.

<figure><img src="../../.gitbook/assets/image (101).png" alt=""><figcaption></figcaption></figure>

After signing up, your Publisher developer account is created, as shown below:

![](<../../.gitbook/assets/Publisher Profile.png>)

Now let's look at the steps to submit your app via the CLI and the Publisher portal.

## Submit an app via CLI

{% hint style="info" %}
Submission through the CLI sends the app in a `draft` state. The publisher must access the Publisher portal to submit the app.
{% endhint %}

1. In the command line, in your app's directory, enter `rc-apps submit`. This packages your app and starts the process of submitting your app for review.

The following questions are displayed on the command line:

2. **Have you logged into our Publisher Portal? (Y/n)** : Enter **Y**.&#x20;
   1. On your browser, the Rocket.Chat cloud tab is opened. Click **Authorize** to allow Rocket.Chat Apps CLI to log in with your Rocket.Chat Cloud Account.&#x20;
   2. You can close the tab that opens after the authorization is complete.
3. **Is this a new App? (Y/n)** : Enter **Y** if your app is new and enter **n** if it is not a new app.
   1. If you enter **n**, the question **What changes were made in this version?** is displayed. Enter the description of the changes to your app.
4. **Is this App free or will it require payment? (Y/n)** : Enter **Y** if your app is free. If your app is a paid app, you must [add it via the Publisher portal](./#submit-an-app-via-publisher-portal).
5. **Please select the categories which apply to this App?** : Select the categories your app belongs to, such as **Design**, **Communication**, **Analytics**, and so on.
6. **Are you ready to submit? (y/N)** : Enter **y** to submit the app.
7. Once your app is submitted, go to the Marketplace Publisher portal. Select **Apps** from the left-hand menu and you can find your app in the **Draft** status.
8. To view your app details, click the **Actions** drop-down menu and select **View Details**. You can also edit the app details and upload an updated version of the app.
9. &#x20;Enter the details about the **Public Changelog** and the **Internal Changelog**.
10. Now, [#enter-the-app-details](./#enter-the-app-details "mention") and then follow the next steps from that section.

## Submit an app via publisher portal

### Package your app

Before submitting your app, you need to package it. Currently, the Rocket.Chat servers and Marketplace allow the submission of `.zip` files. In your app's directory, run the following command:

{% code overflow="wrap" %}
```powershell
rc-apps package --no-compile
```
{% endcode %}

This command will package your app and create a zip file in the `dist` folder. Keep in mind that  `--no-compile` is necessary because you need to submit the source code of the app to the Marketplace for us to evaluate the code, instead of the compiled code that is used to execute the app in the workspace.

### Add your app

To add your app, go to **Apps** > **New App.**

![Apps](<../../.gitbook/assets/publisher-new-app (1).png>)

### **Upload your app package**

Drag and drop your app package or browse your app package `.zip` file and click **Next**.

![Upload App](<../../.gitbook/assets/publish a new app-Upload (1).png>)

### **Enter the app details**

Add the required information for the app:

* Set your app's name under **App Name**.
* Select a category for your app in the **Categories** drop-down.
* Select a Language for your app in the **Languages** drop-down.
* Click **Next.**

<figure><img src="../../.gitbook/assets/publish-app-details.png" alt=""><figcaption><p>App details</p></figcaption></figure>



### **Define the pricing plan**

After entering your app information, the next step is to define the pricing plan and how the users can purchase your app.&#x20;

* **Purchase Type** - You can choose how you plan to distribute your app. The pricing model has three types, `One-time purchase`, `Subscription`, and `Free`.
* **Price** - Enter the price (USD) that you want to set.
* Click **Next.**

{% hint style="info" %}
For a paid app, you must connect with a [Stripe](https://stripe.com/) account before submission. You can find more information at [https://stripe.com/docs/payouts](https://stripe.com/docs/payouts).
{% endhint %}

![Connect Stripe](<../../.gitbook/assets/Connect Stripe.png>)

* **One-time Purchase**: Select **One-time Purchase** when you want your app to have a one-off payment. Your users are allowed to use it forever after that payment.
  * **Price:** Enter the price (USD) you want to set.

{% hint style="info" %}
Your users are allowed to buy the app per workspace. They must purchase the app separately if they have two workspaces and want to use the app in both.
{% endhint %}

* **Subscription:** Select the **Subscription** purchase type when you want your app to be subscription-based.
  * Click **Add pricing plan.** A **New Pricing Plan** pane appears.
  * Choose a **monthly** or **yearly** subscription.
  * Enter the **price** (USD) you want to set.
  * Set the number of days for the trial plan.
  * Click **Save** **Plan.**
  * Once done, click **Next.**
* **Free**: Choose this pricing type when you want your app available to your users for free.&#x20;

### **Upload screenshots**

* **Screenshot**: Upload some images of your app (1200x600 px, maximum of 5 images).
* **Short description**: Provide your app's description.
* **Privacy Policy Summary**: Provide your app users with a summary of the app's privacy and data handling policies.
* **Documentation URL**: Provide a link to your app's documentation.

![Screenshots](../../.gitbook/assets/publish-app-screenshot1.png)

<figure><img src="../../.gitbook/assets/publish-app-screenshot2.png" alt=""><figcaption><p>Screenshot</p></figcaption></figure>

### **Submit your app for review**

Your app is almost ready to submit for review.

* Once you have added the required information, click **Submit for Review.** Our team will review your code and send you a status update via email.

![Submission](../../.gitbook/assets/publish-app-submission.png)

## After app submission

When you upload and submit your app, the app status flow in the portal is as follows:

* **Draft**: After you upload your app, a new submission is created in the **Draft** status. You will receive a  status update via email.
* **Compiling** and **Compiled**: After the publisher fills in the required forms mentioned above, the status changes to **Compiling** and **Compiled**. You will receive a compiled status update via email. The status remains this way until an admin approves or reviews the app.
* **Approval**: Once your app is approved, you will receive an **approved** status update via email, as shown below:

![](../../.gitbook/assets/appsubmission\_approved.png)

* **Reviewed:** In some cases, the app might not be approved and instead receive a review. The publisher receives an email with the app status and the reasons why the app has been reviewed by the admins of the Marketplace.

## Publish your app

Once approved, you can go to the portal and publish your app for users!

To successfully publish an app, you need to follow some guidelines. In the following sections, you can learn about the content and graphic guidelines. You can also see how to register a webhook endpoint link to get updates about your apps.
