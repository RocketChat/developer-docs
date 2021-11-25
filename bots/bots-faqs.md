# Bots FAQs

## I am not trying to stage a denial of service attack, why would I ever want to write a bot?

There are many positive and productive use cases for bots. Imagine a customer service support chat. As soon as a customer enters the support channel, a bot immediately identifies the customer and then:

* fetches recent sales information from the sales dept server
* fetches personal information from the customer data base
* fetches latest notes made by her/his salesperson from the CRM system
* scans the customer's facebook and twitter posts
* obtains details of the last support ticket for this customer

Putting it altogether and then private message the service rep with the information.

Another use-case is a load test bot, imagine a bot that accepts the command:

```
rocketbot loadtest europe 25, asia 50, usa 100, canada 10
```

This command specifies a distribution of test bot instances, to be created across globally located data centers.

Once received, the bot:

* parses the distribution
* concurrently ssh to remote Kubernetes controllers and spawns the specified number of test bot instances to start the load test

## The architecture of hubot-rocketchat looks interesting, can you tell me more about it?

Sure, it is based on hubot-meteorchat. hubot-meteorchat is the hubot integration project for Meteor based chats and real-time messaging systems. Its driver based architecture simplifies creation and customization of adapter for new systems. For example, the hubot-rocketchat integration is just hubot-meteorchat + Rocket.Chat driver.

Learn more about hubot-meteorchat and other available drivers [at this link](https://github.com/Sing-Li/hubot-meteorchat)
