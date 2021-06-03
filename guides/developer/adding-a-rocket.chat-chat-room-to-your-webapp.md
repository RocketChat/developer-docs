---
description: >-
  In this guide, we will see in detail how to add a Rocket.Chat chat room in
  your website/web app in a few minutes.
---

# Adding a Rocket.Chat Chat Room to your WebApp

## **Requirements**

You start with the creation of the Rocket.Chat server and then move on to the integration. A demo app is used to show how to do it concretely.  
To get started you need at least one room and a running Rocket.Chat server. 

In addition to adding a chat room to your web app, this article demonstrates :

* How Rocket.Chat can identify a user through the iframe and therefore handle a login token
* How Rocket.Chat can use an endpoint in your application to identify/create a user
* Use cases with commands and events provided by the RC code once the room has been installed. 

### Create a Rocket.Chat server

There are many ways to create a Rocket.Chat server. A very quick way to do this is via snaps. To start a [server via snaps](https://docs.rocket.chat/installing-and-updating/snaps) on Ubuntu, type in your terminal:

`sudo snap install rocketchat-server`  


Then go to http://localhost:3000 and add the information & settings to launch the Rocket.Chat server.  

## **Part I: Activate the Iframe integration**

To get started, you need to enable the iframe integration setting in your Rocket.Chat server.  
To do so:

1. Click **Administration**

![](https://lh3.googleusercontent.com/KTpOJCvRvDH0Wk2BtXv9P9vbTRsjWIq5tfOtoiFp5grCYI1Ac6KpCq1YHC9A6IdaE_Uqo-c4fKT0vpekrEoZqQe4Igt9LDzTsxWdNXoOQt8vK2n5_D0tZbrfRgoUC1mL8e3kxtN7)

2.  Go to **Settings** and click  **Account**:

![](https://lh5.googleusercontent.com/eWLSuNcpCXOjUMHTdAHq2L5mGJb3n9_t1-BYcV_8tMa04MkFFx6A0Dqg4e5QRLfOVJu_taiuCesdH4R6uQ8tTj-EmRIhp9KXKjB7iuVjr1RYgAhrNUKVakQh19lmcJ1Nma679KaG)

3. In account scroll to the iframe menu and click on the button to enable iframe integration. 

{% hint style="info" %}
This will allow you to integrate iframes from your Rocket.chat server on other websites/web apps
{% endhint %}

![](https://lh3.googleusercontent.com/oJX9R6ItV17TWI8yjmdiTSEBGSYaYAFwUaLnyA1mrOf8KZjfiyM5xvkPPgvsbYtgEq8qKLTcwrp5fB1we5AQH04GsyBzVRTJk-yb15un2fGv2Ilq-K7BR3bjrX43NU0lVEP_eqDG)

Now that iframe integration is enabled in your Rocket.Chat server, we can connect the server to your application.  
****

4. Go to the iframe URL and type in the endpoint API to add an application. Here we type http://localhost:3030/login.  Here you need to put the URL of the application where you want to integrate the current Rocket.Chat application that you have. We used localhost:3030/login as we are running an application on this port for a demo later in the guide.  
****

![](https://lh3.googleusercontent.com/i7PpjihlltdlJLgb4hvEQyqLHpAKWVtfydjhqfqGDk5fMHaLUXTfxgpMYLe85AJ8VYFLsRLoTEJM3cVA9ma298brnjDMqRPabpK0jBcPIuPeGK_NE3EvTOOTqAcJwTjuhgcwUnGl)

5. The second URL we put in is the API URL. It is used so that Rocket.Chat can verify that a user is logged into our application. 

When a user from your website/web app goes to a web page containing the Rockat.chat Room iframe, the Rocket.Chat server will use this API endpoint to verify:

1. The user is identified on your web app
2.  They use the credentials provided to attempt to login into the Rocket.chat server

![](https://lh6.googleusercontent.com/6MIGxTdpld4fcMzUUZ70mcuBkLs6VkOr3yZ5BCdW8HZVvSKkOalu92u1RRHrwwlZ3CrV8v1mRlzvV1uLegBoqXvBHmes41V9C3JHXcFEgdw7ibX9nBtea6K2-8K5W5h0qRwSkU8T)

6. Next, you need to enable the Restrict access inside any Iframe restriction to allow only your application's URL to use the Iframe. 

{% hint style="warning" %}
Disabling this feature is a security hole in your Rocket.Chat server and will allow anyone to load the iframe from your server into their app.
{% endhint %}

To do so:

1. Go to **Settings** &gt;&gt;  **General** and disable **Restrict access inside any Iframe**

![](https://lh5.googleusercontent.com/UThcPkzOsOpXD-VokT2hFYDdB5nd25sNCCey-7tegwXm4MrHj-wiWj0QxYYqPYf_gSSb_cd8TgYGDxAtsZBVE_m_NQ8tdOiTcOmxSa8eab-Ca7vJaatuhyAzRRVJ-XzAb2TidUMc)

7. Hit **Save Changes**

## **Part II: iframe authentification**

In order to use the iframe, the user must have an account and be identified. In this scenario, there are two possibilities:

1. The user already has a Rocket.Chat account
2. The user does not have a Rocket.Chat account

It is explained down below how to manage these two cases and make sure that the Rocket.Chat server can identify the user of the iframe.

You can test the iframe authentication using an example provided by the Rocket.Chat [here](https://github.com/RocketChat/iframe-auth-example).

We will explain the use of the iframe authentication with this demo code, but you are free to do it directly in your application in parallel.

### Steps to use and install the demo code:

1.Clone the code: [https://github.com/RocketChat/iframe-auth-example](https://github.com/RocketChat/iframe-auth-example)

git clone [https://github.com/RocketChat/iframe-auth-example.git](https://github.com/RocketChat/iframe-auth-example.git)

2. Go to the directory of iframe-auth-examples code by typing on your console and open your IDE there:

`cd iframe-auth-examples/`

3. Install the demo packages, type in your console:

`npm install`

{% hint style="info" %}
Do not launch the demo app directly yet because we will modify it a bit! 
{% endhint %}

## **Part III Modifying the demo code:**

Here we will see how to manage to add the iframe to our code. We'll show you how to do this by modifying the demo.

1. Delete from line 129-136 inclusive and replace with:

`res.redirect(“/home”)` 

We do this because we will redirect the user to our home page containing the iframe once he pressed the login button.  


2. On line 89 add:

`app.get('/home', function (req, res) {`

 `res.set('Content-Type', 'text/html');`

 `fs.createReadStream('/home.html').pipe(res);`

`});`  


3. Add a page in ./ called home.html containing this code:  


`<!DOCTYPE html>`

`<html lang="en">`

`<head>`

    `<meta charset="UTF-8">`

    `<meta http-equiv="X-UA-Compatible" content="IE=edge">`

    `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

    `<title>Document</title>`

`</head>`

`<body style="text-align: center;">`

    `<button style="margin-bottom: auto;" onclick={x()}>GO TO GENERAL</button>`

    `<iframe src="http://localhost:3000/channel/general/?layout=embedded" title="myframe"></iframe>`

`</body>`

`<script>`

    `function x() {`

        `document.querySelector("iframe").contentWindow.postMessage(`

            `{`

                `externalCommand: "go",`

                `path: "/channel/general/?layout-embedded"`

            `},`

            `"http://localhost:3000"`

        `);`

    `}`

`</script>`

`</html>`  


So now that a new user is created, they will be redirected to our home.html page.

{% hint style="info" %}
In the Rocket.Chat iframe configuration, we have left POST in the API method. This needs to be tuned with the request methods in our backend for the link we put in the API URL.   
{% endhint %}

It is demo backend for handling the Rocket.Chat server's /sso POST request.   
****The /sso code in our backend will run once the user has been on the page containing the iframe, in this case, it is home.html.  


4. For the demo we will change line 25 to :

var notLoggedIn = false;  


as the user will be logged in as they arrive at this page.    


5. And the line 40:

var currentUsername = true;

Because the user will already be logged in. As a reminder, this only serves the demo code. 

So in this part of the code with /sso, we're going to verify that the user is logged into Rocket.Chat. The code from line 68 onwards shows us that to verify this, we make a post request to the Rocket.Chat server API with the user's credentials. 

{% hint style="info" %}
The login credentials must match those previously entered by the user. For the demo we will put them back as we created them.
{% endhint %}

6. Line 69 and 70, we will put:

`username: 'new-user',`

`password: 'new-users-passw0rd'`  


They were hardcoded for the demo.   


After these modifications, the code is ready for the demonstration.

Type in your console:

`npm run`

This will launch the demo app.  


**Let’s dive a little bit into the code.**

The demo application is currently running on channel 3030. There is the index.js file, that's the backend of our demo. And we also have login.html which is the front-end of the demo.  
Go to the index.js file and look for the get request code on line 84. We see that this code renders the login.html file. In the index.js file, let's take a closer look at the content of the POST /login and POST /sso endpoints which are very important for the iframe integration.

In the code, we see that, after receiving the credentials via the frontend form, we need to pass them through the auth logic of the demo. Here there is no code because it is in a demo, but in your web app, you will certainly have code to manage the auth of your application. 

Once passed into the demo/web app auth logic, the credentials are used to do two things:   


* Either they are used to connect to the Rocket.Chat app via the Rocket.Chat server endpoint /login \(you can copy and paste the demo code into your own app\)
* If Rocket.Chat has not found a user, it creates one with the identifiers received by your application

The home.html file has two important points:

1. The button and the function of the button: We will explain this later in the fast-loading part when we change channels.

2. The iframe: When the user arrives on the page the iframe will load the src of the iframe will call the URL to Rocket.Chat server. After that the Rocket.Chat code will make a request to the sso endpoint we defined earlier. So to:

http://localhost:3030/sso

The code does this to check if the user is logged in or not. This will be handled by the demo backend. 

Once successfully identified Rocket.Chat's code will store a token in its DB to say that the user has logged in \(as usual\) and it will also store the user's credentials in the user's browser local storage.   


So now go to localhost:3030/login and enter any credentials and press Submit:

{% hint style="info" %}
You have to go to a browser in private mode so that the iframe doesn't take your identifiers that are in your local storage, otherwise you will connect with your own account instead of the one that has just been created by our demo app.
{% endhint %}

![](https://lh3.googleusercontent.com/KySYP2MYiHnRMkupsVjzpuVM5vSVEdw59-4l6AdeAv3j2U-JGxx5elvFlEgkHjsYIu75a9DKI_K6uprxHavGbuP1Z0Uh3C_8tBOxJ3SnnDjx-jTsiVmvY-cVZyW74IAucjCn60lI)

After doing all this, you should have the home view in your web app, as shown below:

![](https://lh4.googleusercontent.com/em7OoD309yaQOVI4RjAphBQsuZjVIg-CVdai3rXc6utiMaX7clQqURczLDIc_Oi8I3ZaXWC9LziaMlxVb7Gg3i1CCqId0XuDWPkXP1MX8h_RCz6_vC85wmkT808hOH-P5W_82VC7)

That's a great first step. In the next part, we'll see how to enable fast-loading to switch between rooms.

## **Part 4: Enabling fast-loading for the embedded RC room** 

{% hint style="info" %}
Rocket.Chat is a client side rendered application, so when the user arrives on Rocket.Chat, the whole application loads in their browser, avoiding loading waits when the user changes room for example. 
{% endhint %}

Rocket.Chat is a client-side rendered application, so when the user arrives on Rocket.Chat, the whole application loads in their browser, avoiding loading waits when the user changes room for example. 

The problem is that this is not the case in the iframe. So if the user switches rooms in the iframe, there will be latency. We want to remove this latency and make the iframe load completely when the user goes to the page. 

Rocket.Chat provides commands for iframe integration. In these commands, there is postMessage\(\). Using this command in your client-side code, the iframe contentWindow will client-side route to a chat room thus making the switching instant without any loading.

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-integration-sending-commands" %}

In order to use these commands, which we will demonstrate next, you need to change a setting in your Rocket.Chat server. To change it:  


1. Go to **Administration**:

![](https://lh3.googleusercontent.com/KTpOJCvRvDH0Wk2BtXv9P9vbTRsjWIq5tfOtoiFp5grCYI1Ac6KpCq1YHC9A6IdaE_Uqo-c4fKT0vpekrEoZqQe4Igt9LDzTsxWdNXoOQt8vK2n5_D0tZbrfRgoUC1mL8e3kxtN7)

2. Go to **Settings** &gt; **General** &gt; **iframe Integration**:  


In iframe integration, check **Enable Recieve**.

In the **Receive Origin** field, you should put the URL of your web app that will receive the commands. As we are working with the demo, we have put localhost:3030:

![](https://lh6.googleusercontent.com/eqR0uGFZcTDbJuaypQfOK6OdAwEmnDdon8_31LIhUylXEXc3QcQwfdXATR7B9Lg5uh7Xdaa9R_DFqOr7GPgS4TjKLhBiKr6L9Qhy7Mb_D6MJr3RpuEl8k1SvxxiHRacpwcouo9Ql)

Once saved, this will allow the iframe's parent window to send commands to the Rocket.Chat server.

Then go back to the code, in home.html.

You can review the function we have hooked. Click **Go To General** button:  


        `document.querySelector("iframe").contentWindow.postMessage(`

            `{`

                `externalCommand: "go",`

                `path: "/channel/general/?layout-embedded"`

            `},`

            `"`[`http://localhost:3000`](http://localhost:3000) `<Your server URL>"`

        `);`  


This command will go directly to the general room of the Rocket.chat server. 

So now, once permission has been enabled in your server, it allows you to change rooms without loading. 

And there you have it, you are now ready to add a chat room to your web app.  
  


However, Rocket.Chat provides more than just the ability to have an embedded room. Indeed, using the  application code and server permissions, one can use certain commands \(like the go to room we used\) and events triggered by the embedded application. 

For more details about events and commands go to:  


{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-integration-sending-commands" %}

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-events" %}

We will see some use cases of how to use them in the next points

## **Part 5: Uses cases**

### **Use case 1 - Commands: Change your user status**

We will demo another example of the commands:  
Go to home.html and add the x\(\) function to the tag script:

`const x = () => {`

    `document.getElementsByTagName("iframe")[0].contentWindow.postMessage({` 

        `externalCommand: "set-user-status",` 

        `status: "away"`

    `},`

    `"http://localhost:3000"`

    `)`

`}`

Then replace the &lt;button&gt; line in home.html with:

&lt;button style="margin-bottom: auto;" onclick={x\(\)}&gt;Set away status&lt;/button&gt;  


Now once you are in the embedded room, you can click on the button and it will change your status. ****

### **Use case 2 : Events: Adding code for Rocket.Chat iframe events**

Rocket.Chat provides events in the iframe. These events trigger different actions by the user. You can get the full list here:

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-events" %}

However, we'll do a use case with an event so you can see how it works:

First, to enable the sending of iframe events, you need to enable the feature in your Rocket.Chat app:

1. Go to **Administration** 

![](https://lh3.googleusercontent.com/KTpOJCvRvDH0Wk2BtXv9P9vbTRsjWIq5tfOtoiFp5grCYI1Ac6KpCq1YHC9A6IdaE_Uqo-c4fKT0vpekrEoZqQe4Igt9LDzTsxWdNXoOQt8vK2n5_D0tZbrfRgoUC1mL8e3kxtN7)

2. Go to _**Settings**_ &gt; **General** &gt; **Iframe Integration:**

3. Toggle switch **Enable Send** on.

![](https://lh3.googleusercontent.com/P4dzEktfFii-FfgRrgmQfqLOwdzeWZ84ZYe2Mf9CiZRckmt5DmGB6X0Uof1yXzwVkAesTf-GecSUf-kI1prWmCThrYFsFotrsiLcxuTuZ_TC5cxwaBKAQzMz02YmZCVeEzIgK3th)

This is to allow your Rocket.Chat server to send events to the parent window of the iframe. In the **Send Target Origin** field, you can put a \* or the URL of your application. Click **Save Changes**

3. In home.html in the tag script, add:  


    `window.addEventListener('message', function(e) {`

    `if(e.data.eventName === 'room-opened') {`

        `alert('You opened a room!')`

    `}`

`});`  


Go in your embedded room, and type \#&lt;ARoomName&gt; in the message field:

![](https://lh3.googleusercontent.com/pqpYgrztznStOyNigJwm1YSAcyOkRro3ytTWS8a2Wn-6C9ww9puIMbZI0GOTeEyOPI3sxdtc3c33sDPA8yzaa5KzfH3Yn60ksef0huzS5TVU69hynxMeIk0AKCb49aJy8tdqYJpW)

Hit **Enter**.

Now, if you click on the link and thus open a new room, an alert should appear on your screen:

![](https://lh3.googleusercontent.com/s-vN3AiSbbqkNMWkgyMa5Obf2q44QQ2nMyCHCFadmIgz5kKDsnvAD_TABcLccRLCXcLg8spvStZiA6WFp-xCdicMiMp48G5VU-itqE9mKdjOTl5qJ9vKgz85hL3nBYyajk_HwH7z)

### **Use Case 3 - Enable / Disable embedded layout**

Currently, we see that the application is in embedded mode. That is, we only see the room we are in and the left sidebar and room header are not present. 

However, we can make the user see your whole Rocket.Chat application in your web app. 

To do this you need to change a line in the iframe tag to enable or disable the embedded layout:  


**Enable embedded layout:** 

`<iframe style="width: 100%; height: 80vh;" src="http://localhost:3000/channel/ChannelTest1/?layout=embedded" title="myframe"></iframe>`  


**Disable embedded layout:**

`<iframe style="width: 100%; height: 80vh;" src="http://localhost:3000/channel/ChannelTest1" title="myframe"></iframe>`  


The result after deactivating it will be like this :

![](https://lh3.googleusercontent.com/a1ja1ER2gcQ-u7OqLvgIGhldR4j2hLZTON4fuI0H5sOxaVFbGj8eRxx275XUGel6gx5DGeancyVND4pkxaUM7tdjae3z4tUVkejdJYUPDTgfl4HuBABMZdjCWs38ANTahEB1DhYe)

