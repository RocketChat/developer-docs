---
description: >-
  In this guide, we will see in detail how to add a Rocket.Chat chat room in
  your website/web app in a few minutes.
---

# Adding a Rocket.Chat Chat Room to your Web App

## **Requirements**

You start with the creation of the Rocket.Chat server and then move on to the integration. A demo app is used to show how to do it concretely.\
To get started, you need at least one room and a running Rocket.Chat server.

In addition to adding a chat room to your web app, this article demonstrates :

* How Rocket.Chat can identify a user through the iframe and therefore handle a login token.
* How Rocket.Chat can use an endpoint in your application to identify/create a user.
* Use cases with commands and events provided by the RC code once the room has been installed.

### Create a Rocket.Chat server

There are many ways to create a Rocket.Chat server. A quick way to do this is via snaps. To start a [server via snaps ](https://docs.rocket.chat/quick-start/installing-and-updating/rapid-deployment-methods/snaps)on Ubuntu, type in your terminal:

`sudo snap install rocketchat-server`\\

Then go to http://localhost:3000 and add the information & settings to launch the Rocket.Chat server.

## **Part I: Activate the Iframe Integration**

To get started, you need to enable the iframe integration setting in your Rocket.Chat server.

1. Click **Administration > Settings > Accounts**
2. In account, scroll to the iframe menu and click on the button to enable iframe integration.

{% hint style="info" %}
This will allow you to integrate iframes from your Rocket.chat server on other websites/web apps.
{% endhint %}

Now that iframe integration is enabled in your Rocket.Chat server, we can connect the server to your application.\\

***

3\. Go to the **iframe URL** and type in the endpoint API to add an application. Here we type http://localhost:3030/login. Here you need to put the URL of the application where you want to integrate the current Rocket.Chat application that you have. We used localhost:3030/login as we are running an application on this port for a demo later in the guide.\\

***

![](<../../.gitbook/assets/image (51).png>)

4\. The second URL we put in is the API URL. It is used so that Rocket.Chat can verify that a user is logged into our application.

When a user from your website/web app goes to a web page containing the Rocket.Chat Room iframe, the Rocket.Chat server will use this API endpoint to verify:

i. The user is identified on your web app.

ii. They use the credentials provided to attempt to login into the Rocket.Chat server.

![](https://lh6.googleusercontent.com/6MIGxTdpld4fcMzUUZ70mcuBkLs6VkOr3yZ5BCdW8HZVvSKkOalu92u1RRHrwwlZ3CrV8v1mRlzvV1uLegBoqXvBHmes41V9C3JHXcFEgdw7ibX9nBtea6K2-8K5W5h0qRwSkU8T)

5\. Next, you need to enable the Restrict access inside any Iframe restriction to allow only your application's URL to use the Iframe.

{% hint style="warning" %}
Disabling this feature is a security hole in your Rocket.Chat server and will allow anyone to load the iframe from your server into their app.
{% endhint %}

Go to **Administration > Settings > General** and disable **Restrict access inside any Iframe**

![](https://lh5.googleusercontent.com/UThcPkzOsOpXD-VokT2hFYDdB5nd25sNCCey-7tegwXm4MrHj-wiWj0QxYYqPYf\_gSSb\_cd8TgYGDxAtsZBVE\_m\_NQ8tdOiTcOmxSa8eab-Ca7vJaatuhyAzRRVJ-XzAb2TidUMc)

Hit **Save Changes**

## **Part II: iframe authentification**

To use the iframe, the user must have an account and be identified. In this scenario, there are two possibilities:

1. The user already has a Rocket.Chat account
2. The user does not have a Rocket.Chat account

It is explained down below how to manage these two cases and make sure that the Rocket.Chat server can identify the user of the iframe.

You can test the iframe authentication using an example provided by the Rocket.Chat [here](https://github.com/RocketChat/iframe-auth-example).

We will explain the use of the iframe authentication with this demo code, but you are free to do it directly in your application in parallel.

### Steps to use and install the demo code:

1. Clone the code: [https://github.com/RocketChat/iframe-auth-example](https://github.com/RocketChat/iframe-auth-example)

git clone [https://github.com/RocketChat/iframe-auth-example.git](https://github.com/RocketChat/iframe-auth-example.git)

2\. Go to the directory of iframe-auth-examples code by typing on your console and open your IDE there:

`cd iframe-auth-examples/`

3\. Install the demo packages, type in your console:

`npm install`

{% hint style="info" %}
Do not launch the demo app directly yet because we will modify it a bit!
{% endhint %}

## **Part III Modifying the demo code:**

Here we will see how to manage to add the iframe to our code. We'll show you how to do this by modifying the demo.\\

### 1. Replace the code of the _index.js_ file with this code:

```javascript
//
var express = require('express');
var bodyParser = require('body-parser');
var axios = require('axios');
var fs = require('fs');
var app = express();

app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());

// CORS in case you need
app.use((req, res, next) => {
 res.set('Access-Control-Allow-Origin', 'http://localhost:3000'); // this is the rocket.chat URL
 res.set('Access-Control-Allow-Credentials', 'true');

 next();
});

// this is the endpoint configured as API URL
app.post('/sso', function (req, res) {

 // add your own app logic here to validate user session (check cookies, headers, etc)

 // if the user is not already logged in on your system, respond with a 401 status
 var notLoggedIn = false;
 if (notLoggedIn) {
 return res.sendStatus(401);
 }

 // you can save the token on your database as well, if so just return it
 // MongoDB - services.iframe.token
 var savedToken = null;
 if (savedToken) {
 return res.json({
 token: savedToken
 });
 }

 // if dont have the user created on rocket.chat end yet, you can now create it
 var currentUsername = true;
 if (!currentUsername) {
 axios.post('http://localhost:3000/api/v1/users.register', {
 username: 'new-user',
 email: 'mynewuser@email.com',
 pass: 'new-users-passw0rd',
 name: 'New User'
 }).then(function (response) {

 // after creation you need to log the user in to get the `authToken`
 if (response.data.success) {
 return axios.post('http://localhost:3000/api/v1/login', {
 username: 'new-user',
 password: 'new-users-passw0rd'
 });
 }
 }).then(function (response) {
 if (response.data.status === 'success') {
 res.json({
 loginToken: response.data.data.authToken
 });
 }
 }).catch(function (error) {
 res.sendStatus(401);
 });
 } else {

 // otherwise create a rocket.chat session using rocket.chat's API
 axios.post('http://localhost:3000/api/v1/login', {
 username: 'new-user',
 password: 'new-users-passw0rd'
 }).then(function (response) {
 if (response.data.status === 'success') {
 res.json({
 loginToken: response.data.data.authToken
 });
 }
 }).catch(function() {
 res.sendStatus(401);
 });
 }
});

// just render the form for the user authenticate with us
app.get('/login', function (req, res) {
 res.set('Content-Type', 'text/html');
 fs.createReadStream('login.html').pipe(res);
});

app.get('/home', function (req, res) {
 res.set('Content-Type', 'text/html');
 fs.createReadStream('home.html').pipe(res);
});

// receives login information
app.post('/login', function (req, res) {

 // do your own authentication process

 // after the user is authenticated we can proceed with authenticating him on rocket.chat side

 //
 //
 // the code below is exactly the same as the on /sso endpoint, except for its response
 // it was duplicated for understanding purpose
 // the authentication process and is a well-designed app =)
 //
 //

 // if dont have the user created on rocket.chat end yet, you can now create it
 var currentUsername = null;
 if (!currentUsername) {
 axios.post('http://localhost:3000/api/v1/users.register', {
 username: 'new-user',
 email: 'mynewuser@email.com',
 pass: 'new-users-passw0rd',
 name: 'New User'
 }).then(function (response) {

 // after creation you need to log the user in to get the `authToken`
 if (response.data.success) {
 return axios.post('http://localhost:3000/api/v1/login', {
 username: 'new-user',
 password: 'new-users-passw0rd'
 });
 }
 }).then(function (response) {
 if (response.data.status === 'success') {
 res.redirect('/home')
 }
 }).catch(function (error) {
 res.sendStatus(401);
 });
 } else {

 // otherwise create a rocket.chat session using rocket.chat's API
 axios.post('http://localhost:3000/api/v1/login', {
 username: 'username-set-previously',
 password: 'password-set-previously'
 }).then(function (response) {
 if (response.data.status === 'success') {

 // since this endpoint is loaded within the iframe, we need to communicate back to rocket.chat using `postMessage` API
 res.set('Content-Type', 'text/html');
 res.send(`<script>
 window.parent.postMessage({
 event: 'login-with-token',
 loginToken: '${ response.data.data.authToken }'
 }, 'http://localhost:3000'); // rocket.chat's URL
 </script>`);
 }
 }).catch(function() {
 res.sendStatus(401);
 });
 }
});

app.listen(3030, function () {
  console.log('Example app listening on port 3030!');
});
```

### 2. Add a file in ./ called home.html containing this code:

```html
//
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body style="text-align: center;">
    <button style="margin-bottom: auto;" onclick={x()}>GO TO GENERAL</button>
    <iframe src="http://localhost:3000/channel/general/?layout=embedded" title="myframe"></iframe>
</body>
<script>
    function x() {
        document.querySelector("iframe").contentWindow.postMessage(
            {
                externalCommand: "go",
                path: "/channel/general/?layout=embedded"
            },
            "http://localhost:3000"
        );
    }
</script>
</html>
```

So now that a new user is created, they will be redirected to our home.html page.\\

{% hint style="info" %}
In the Rocket.Chat **Administration > Settings > Accounts > Iframe**, we have left POST in the API method. This needs to be tuned with the request methods in our backend for the link we put in the API URL. (The demo backend for handling the Rocket.Chat server's /sso POST request)\\
{% endhint %}

In index.js, the app.post('/sso' code in our backend will only be run once the user has been on the page containing the iframe, in this case, it is home.html.\\

Also in index.js, the app.post('/sso' code, we're going to verify that the user is logged into Rocket.Chat. The code from axios.post('http://localhost:3000/api/v1/login' onwards shows us that to verify this, we make a post request to the Rocket.Chat server API with the user's credentials. \\

{% hint style="info" %}
The login credentials must match those previously entered by the user. For the demo, we will put them back as we created them.
{% endhint %}

\
After these modifications, the code is ready for the demonstration.

Type in your console:

`npm run start`

This will launch the demo app.

Let’s dive a little bit more in the code:

The demo application is currently running on channel 3030.

There is the index.js file, that's the backend of our demo. And we also have login.html which is the front-end of the demo.

In the index.js file, let's take a closer look at the content of the POST /login and POST /sso endpoints which are very important for the iframe integration.\\

In the code, we see that, after receiving the credentials via the frontend form, we need to pass them through the auth logic of the demo. Here there is no code because it is in a demo, but in your web app, you will certainly have code to manage the auth of your application.

Once passed into the demo/web app auth logic, the credentials are used to do two things: \\

* Either they are used to connect to the Rocket.chat app via the Rocket.Chat server endpoint /login (you can copy and paste the demo code into your own app)
* If Rocket.chat has not found a user, it creates one with the identifiers received by your application

The home.html file has two important points:

1\. The button and the function of the button: We will explain this later in the fast-loading part when we change channels.

2\. The iframe: When the user arrives on the page the iframe will load the src of the iframe and will call the URL to Rocket.Chat server. After that the Rocket.Chat code will make a request to the sso endpoint we defined earlier. So to:

http://localhost:3030/sso

The code does this to check if the user is logged in or not. This will be handled by the demo backend.

Once successfully identified Rocket.Chat code will store a token in its DB to say that the user has logged in (as usual) and it will also store the user's credentials in the user's browser local storage. \\

So now go to localhost:3030/login and enter any credentials and hit Submit:

{% hint style="info" %}
You have to go to a browser in private mode so that the iframe doesn't take your identifiers that are in your local storage, because otherwise, you will connect with your own account instead of the one that has just been created by our demo app.
{% endhint %}

![](https://lh3.googleusercontent.com/KySYP2MYiHnRMkupsVjzpuVM5vSVEdw59-4l6AdeAv3j2U-JGxx5elvFlEgkHjsYIu75a9DKI\_K6uprxHavGbuP1Z0Uh3C\_8tBOxJ3SnnDjx-jTsiVmvY-cVZyW74IAucjCn60lI)

You can see Rocket.Chat's home screen in your web app.

That's a great first step. In the next part, we'll see how to enable fast-loading to switch between rooms.

**Part IV: Enabling fast-loading for the embedded RC room**\\

{% hint style="info" %}
Rocket.Chat is a client-side rendered application, so when the user arrives on Rocket.Chat, the whole application loads in their browser, avoiding loading waits when the user changes the room.
{% endhint %}

Rocket.Chat is a client-side rendered application, so when the user arrives on Rocket.Chat, the whole application loads in their browser, avoiding loading waits when the user changes the room.

The problem is that this is not the case in the iframe. So if the user switches rooms in the iframe, there will be latency. We want to remove this latency and make the iframe load completely when the user goes to the page.

Rocket.Chat provides commands for iframe integration. In these commands, there is postMessage(). Using this command in your client-side code, the iframe content Window will client-side route to a chat room, making the switching instant without any loading.

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-integration-sending-commands" %}

To use these commands, which we will demonstrate next, you need to change a setting in your Rocket.Chat server. To change it:\
Go to **Administration > Settings > General > iframe Integration** check **Enable Recieve**.

In the **Receive Origin** field, you should put the URL of your web app that will receive the commands. As we are working with the demo, we have put localhost:3030:

![](<../../.gitbook/assets/image (85).png>)

Once saved, this will allow the iframe's parent window to send commands to the Rocket.Chat server.

Then go back to the code, in home.html.

You can review the function we have hooked. Click **Go To General** button:\\

`document.querySelector("iframe").contentWindow.postMessage(`

`{`

`externalCommand: "go",`

`path: "/channel/general/?layout-embedded"`

`},`

`"`[`http://localhost:3000`](http://localhost:3000) `<Your server URL>"`

`);`\\

This command will go directly to the general room of the Rocket.chat server.

So now, once permission has been enabled in your server, it allows you to change rooms without loading.

And there you have it; you are now ready to add a chat room to your web app.\\

However, Rocket.Chat provides more than just the ability to have an embedded room. Indeed, using the application code and server permissions, one can use certain commands (like the go-to room we used) and events triggered by the embedded application.

For more details about events and commands, go to:\\

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-integration-sending-commands" %}

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-events" %}

We will see some use cases of how to use them in the next points.

## **Part V: Uses cases**

### **Use case 1 - Commands: Change your user status**

We will demo another example of the commands:\
Go to home.html and add the x() function to the tag script:

```html
const x = () => {
    document.getElementsByTagName("iframe")[0].contentWindow.postMessage({ 
        externalCommand: "set-user-status", 
        status: "away"
    },
    "http://localhost:3000"
    )
}
```

Then replace the \<button> line in home.html with:

```
<button style="margin-bottom: auto;" onclick={x()}>Set away status</button>
```

Once you are in the embedded room, you can click on the button and change your status. \*\*\*\*

### **Use case 2 : Events: Adding code for Rocket.Chat iframe events**

Rocket.Chat provides events in the iframe. These events trigger different actions by the user. You can get the full list here:

{% embed url="https://developer.rocket.chat/guides/developer/iframe-integration/iframe-events" %}

However, we'll do a use case with an event so you can see how it works:

First, to enable the sending of iframe events, you need to enable the feature in your Rocket.Chat app:

1. Go to **Administration > \_Settings**\_\*\* > General > Iframe Integration\*\*
2. Toggle switch **Enable Send** on.

This is to allow your Rocket.Chat server to send events to the parent window of the iframe. In the **Send Target Origin** field, you can put a \* or the URL of your application. Click **Save Changes**

3\. In home.html in the tag script, add:

```html
 window.addEventListener('message', function(e) {
    if(e.data.eventName === 'room-opened') {
        alert('You opened a room!')
    }
});
```

Go in your embedded room, and type #\<ARoomName> in the message field:

![](https://lh3.googleusercontent.com/pqpYgrztznStOyNigJwm1YSAcyOkRro3ytTWS8a2Wn-6C9ww9puIMbZI0GOTeEyOPI3sxdtc3c33sDPA8yzaa5KzfH3Yn60ksef0huzS5TVU69hynxMeIk0AKCb49aJy8tdqYJpW)

Hit **Enter**.

Now, if you click on the link and thus open a new room, an alert should appear on your screen:

![](https://lh3.googleusercontent.com/s-vN3AiSbbqkNMWkgyMa5Obf2q44QQ2nMyCHCFadmIgz5kKDsnvAD\_TABcLccRLCXcLg8spvStZiA6WFp-xCdicMiMp48G5VU-itqE9mKdjOTl5qJ9vKgz85hL3nBYyajk\_HwH7z)

### **Use Case 3 - Enable / Disable embedded layout**

Currently, we see that the application is in embedded mode. We only see the room we are in\*\*,\*\* and the left sidebar and room header are not present.

However, we can make the user see your whole Rocket.Chat application in your web app.

To do this you need to change a line in the iframe tag to enable or disable the embedded layout:\\

**Enable embedded layout:**

```
<iframe style="width: 100%; height: 80vh;" src="http://localhost:3000/channel/ChannelTest1/?layout=embedded" title="myframe"></iframe>
```

**Disable embedded layout:**

```
<iframe style="width: 100%; height: 80vh;" src="http://localhost:3000/channel/ChannelTest1" title="myframe"></iframe>
```

The result after deactivating it will be like this :

![](https://lh3.googleusercontent.com/a1ja1ER2gcQ-u7OqLvgIGhldR4j2hLZTON4fuI0H5sOxaVFbGj8eRxx275XUGel6gx5DGeancyVND4pkxaUM7tdjae3z4tUVkejdJYUPDTgfl4HuBABMZdjCWs38ANTahEB1DhYe)
