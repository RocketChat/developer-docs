---
description: Welcome to our Error Reporting Guide
---

# Contribute Through Bug Reporting

We're thrilled to have you here! To ensure a smooth and efficient bug-reporting process, we've put together this guide. Please take a moment to familiarize yourself with our practices and procedures.

### Identifying Bugs

Before you proceed, it's crucial to ascertain whether what you're encountering is indeed a bug. If you're struggling to understand how to perform a task, experiencing problems accessing your server, unable to install the server or want a new widget in Rocket.Chat, these are not considered bugs.

{% hint style="success" %}
If your concern aligns with the non-bug category, kindly refer to the provided resources in our [documentation](https://docs.rocket.chat/). Suggestions for new features should be submitted in the [forums](https://forums.rocket.chat).
{% endhint %}

### Before Reporting a Bug

Before you report a new issue, please:

* Thoroughly read the [documentation](https://docs.rocket.chat/).
* Ensure you're running the latest version of Rocket.Chat. An update might resolve your issue.
* Try to identify reproducible steps. If we can reproduce it, we can fix it faster.
* Check all your logs for errors. See the [#gathering-logs](contribute-through-bug-reporting.md#gathering-logs "mention") section for guidance.
* [Search the Forums](https://forums.rocket.chat) using a few different search terms.
* [Search the Issues](https://github.com/RocketChat/Rocket.Chat/issues) for your bug. If you find it, carefully check that it is identical and give it a thumbs up, or add some additional information to the ticket if it differs. This will help give us a fuller picture.

If you've done all of the above and still need to report a bug, please proceed.

### How to Report a Bug?

Giving clear background information will help save a lot of time. When reporting a new bug, please include the following information to promote effective bug fixing:

* Operating System / Version / Architecture (64-bit?)
* Browser type and version, including any add-ons. (e.g., AdBlocker, NoScript, etc.)
* Rocket.Chat version
* Expected behavior
* Actual behavior
* Steps to reproduce the bug consistently
* Relevant errors and other log output
* Screenshots, if applicable

{% hint style="info" %}
You can register your bug at the following places based on the platform you're using:

[Rocket.Chat Server](https://github.com/RocketChat/Rocket.Chat/issues/new/choose)

[Rocket.Chat Mobile Apps](https://github.com/RocketChat/Rocket.Chat.ReactNative/issues/new)

[Rocket.Chat Electron desktop app](https://github.com/RocketChat/Rocket.Chat.Electron)
{% endhint %}

{% hint style="info" %}
#### Determining Rocket.Chat Version

You can find your Rocket.Chat version in two ways:

* As an Admin, log into your Rocket.Chat. Navigate to **Administration -> Workspace -> Info**
* Append `/api/info` to your Rocket.Chat URL
{% endhint %}

{% hint style="info" %}
**Gathering Logs**

* **Browser Logs**: To collect logs from your browser, press Ctrl/Cmd + Shift + j. Errors will appear in red.
* **Server Logs**: As an Admin, log into your Rocket.Chat. Navigate to **Administration -> Workspace -> View Logs** It's often helpful to open this in another browser, reproduce the issue, and observe any exceptions that pop up in the logs. Don't forget to check your web server logs and general system logs as well.
{% endhint %}

We appreciate your effort in helping us improve our software. Thank you for your contribution!
