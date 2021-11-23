---
description: >-
  Understanding how and where you need to deploy your first Rocket.Chat instance
  to get started!
---

# Choosing a Deployment Host

## Introduction

For creating their own chat server, one might think of the process of the standard chat platforms like slack, discord, or telegram where they have to open up the app or go to one of their links, open an account and it's done. Although you can do the same with the Rocket.Chat Cloud version, one of the unique advantages of Rocket.Chat is the ability to self-host it in an air-gapped environment. This gives the user power to own their data, have it securely placed with their own servers. With these standard platforms, you're not creating your "own" server, you're just creating a space within theirs, which gives them the absolute power to use your data however they like.

{% hint style="info" %}
One of the unique advantages of Rocket.Chat is the ability to self-host it in an air-gapped environment.
{% endhint %}

## What is deployment?

Deployment is another fancy word for installation. If you have ever installed an app on your phone, or software on your PC, you have already kind of deployed something.

Deployment in this context means installing and setting your Rocket.Chat server up for usage.

## Deployment method vs Deployment platform

Deployment methods and platforms are frequently confused, however. they are quite distinct from one another.&#x20;

* To know the method of a deployment, you need to ask _“how is xyz deployed?” _
* To know the platform of a deployment, you need to ask _“where is xyz deployed?”_

**Examples of Deployment Methods:** Manual Installation, Snap, Docker, Ansible, etc.&#x20;

**Examples of Deployment Platforms: **AWS, Digital Ocean, GCP

**Kubernetes** is an example of both. It is a deployment method because we’re using Kubernetes tools to deploy an app, but it can also be interpreted as a platform because once we have a k8s cluster ready, with certain ways the whole methodological aspect can be abstracted away (e.g. using helm).

## Score

We want you to have a solid idea of which method/platform to use for your use case, which is why we’ve come up with these scoring criteria. Following are a few characteristics that one needs to score each deployment. Scoring is necessary because each method and platform is different and is better suited for different situations.

### Scalability

The ability to scale or the ability to handle a growing amount of work.&#x20;

#### What does it mean?

Consider you and your three friends going on a trip. You’ll be good to rent just a single four-wheeler to accommodate you all. Now say, suddenly, all of your friends’ families wanted to join in as well. Now you have two options, either rent a bigger car or rent more cars.

By increasing the resources or in this case the ability to travel more people you have just scaled your traveling solution. This also applies to Rocket.Chat. On a decently beefed server, a single Rocket.Chat instance may be able to handle a thousand simultaneous online users. But what if your community or company increases its members by a thousand more? Similar to the previous example you either need to turn the server to something even beefier or get more Rocket.Chat servers to handle those extra users.

There are two kinds of scaling, vertical and horizontal. Vertical scaling is synonymous with “getting a bigger car” or in this case allocating more resources to the same server. Horizontal scaling is synonymous with “getting more cars” or in this case adding more nodes or more Rocket.Chat instances to handle those increased number of users.

### **Ease of deployment**

Self-explanatory to some extent: Just answer the question, how easy is the process of deployment of your own server & its database.

### **Ease of maintenance**

Similar to _ease of deployment_, ease of maintenance is the answer to the question - How easy is the process of maintaining the server? By maintenance, we refer to the processes of updating server requirements, patching security fixes, updating the components, etc.

### Official support

Most if not all methods and platforms discussed in our documentation are officially supported, yet, some of the things when grading this characteristic are, update frequency, bug resolutions, feature implementations, and community support.
