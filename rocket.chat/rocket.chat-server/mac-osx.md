# Mac OSX

You can set up and run a Rocket.Chat development environment on your Mac OSX.

{% hint style="info" %}
This setup instruction has been tested on MacBook Pro 2015, 8Gig Ram, 512Gb SSD,i5
{% endhint %}

{% hint style="success" %}
Currently, Rocket.Chat uses at least `meteor 2.5.6` which has support for M1 chips. If you are to run an environment with a lesser version, consider using[ the Rosetta terminal](https://support.apple.com/en-us/HT211861) for M1 chips.
{% endhint %}

* Install Meteor by executing:

```
curl https://install.meteor.com/ | sh
```

Meteor comes pre-installed with npm and node, verify by executing:

```
meteor node -v
meteor npm -v
```

* Install Yarn if you don't already have it on your system. Yarn is the recommended package manager

```
npm install --global yarn
```

{% hint style="success" %}
Information on the various versions of packages needed can be found in the `package.json`
{% endhint %}

* To easily manage the node versions on your machine, install the [n node package manager](https://www.npmjs.com/package/n) and switch to the desired node version you want to use

```
npm install -g n
n 14.18.3
node -v
```

* Fork and clone the Rocket.Chat repository [https://github.com/RocketChat/Rocket.Chat](https://github.com/RocketChat/Rocket.Chat) and navigate into the directory

```
git clone https://github.com/your-username/Rocket.Chat
cd Rocket.Chat
```

* Install all the packages by simply running

```
yarn
```

* Startup your development server by executing

```
yarn dev
```

When done, you should see the following printed on your terminal and the local server running on `http://localhost:3000`

![Rocket.Chat server successfully running on MacOSX](../../.gitbook/assets/RocketChat-server-successfully-running-on-MacOSX)
