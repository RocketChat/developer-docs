# Get Channels

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieve all channels and the number of messages in each channel within a specific period. It supports only the offset and count parameters for [#pagination](../../../../#pagination "mention").

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                         | Requires Auth | HTTP Method |
| ------------------------------------------- | ------------- | ----------- |
| `api/v1/engagement-dashboard/channels/list` | `yes`         | `GET`       |

## &#x20;Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code></td><td><code>2023-05-20T00:00:00.000Z</code></td><td>Required</td><td>The start date.</td></tr><tr><td><code>end</code></td><td><code>2023-05-30T00:00:00.000Z</code></td><td>Required</td><td>The end date.</td></tr></tbody></table>



## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/channels/list?start=2023-05-20T00%3A00%3A00.000Z&end=2023-05-30T00%3A00%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'

```

## Example Result

### Success

```json
{
    "channels": [
        {
            "room": {
                "_id": "gqNboSNK6PXYbdYufkCyNkxbuHQjAKnC7F",
                "ts": "2023-05-19T19:38:14.112Z",
                "t": "d",
                "_updatedAt": "2023-06-01T15:20:05.886Z",
                "usernames": [
                    "google-calendar.bot",
                    "pavithra.sudhakar"
                ]
            },
            "messages": 178,
            "lastWeekMessages": 92,
            "diffFromLastWeek": 86
        },
        {
            "room": {
                "_id": "kCyNkxbuHQjAKnC7FrbAXPnMktTFbNpwtJ",
                "ts": "2023-03-16T14:42:19.817Z",
                "t": "d",
                "_updatedAt": "2023-06-01T08:50:02.427Z",
                "usernames": [
                    "funke.olasupo",
                    "google-calendar.bot"
                ]
            },
            "messages": 4,
            "lastWeekMessages": 9,
            "diffFromLastWeek": -5
        },
        {
            "room": {
                "_id": "kdgf7sgLvwBri9rtArocket.cat",
                "ts": "2023-03-25T02:00:12.662Z",
                "t": "d",
                "_updatedAt": "2023-05-21T02:00:13.344Z",
                "usernames": [
                    "faria.masood",
                    "rocket.cat"
                ]
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "6401c3b9fa0ed7dd90509361rYhzFRd2QZjNwAAXX",
                "ts": "2023-03-03T09:54:01.389Z",
                "t": "d",
                "_updatedAt": "2023-03-03T09:54:36.616Z",
                "usernames": [
                    "rcuser01:matrix.org",
                    "rodriq"
                ]
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "umHTBCNbqdJsW9yw9",
                "name": "pri1",
                "ts": "2023-04-27T17:17:54.563Z",
                "t": "p",
                "_updatedAt": "2023-04-27T17:23:35.156Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "yuKgXBqdnzqXF6T9Y",
                "name": "Test",
                "ts": "2023-02-06T13:28:25.027Z",
                "t": "c",
                "_updatedAt": "2023-05-12T14:06:34.033Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "b66oZ8i9pkeSko33vrYhzFRd2QZjNwAAXX",
                "ts": "2023-05-12T14:10:34.290Z",
                "t": "d",
                "_updatedAt": "2023-05-12T14:10:38.217Z",
                "usernames": [
                    "guester",
                    "rodriq"
                ]
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "M58HfkJqaKbD2piHh",
                "name": "qxSdmSNc4WQsZbeAm",
                "ts": "2023-03-13T14:34:21.643Z",
                "t": "p",
                "_updatedAt": "2023-03-13T15:38:37.273Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "nf52k8bpJ8y7oHmwk",
                "name": "Test",
                "ts": "2023-04-05T15:09:59.801Z",
                "t": "l",
                "_updatedAt": "2023-04-05T15:14:44.768Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "Z8KjZi7rvFqNqwTpd",
                "name": "Folorunso Yewande Susan",
                "ts": "2023-03-31T15:12:58.431Z",
                "t": "l",
                "_updatedAt": "2023-03-31T15:22:33.764Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "huQs44zbCmozm4XtW",
                "name": "te7ZH24Evmx4mXiMg",
                "ts": "2023-03-13T00:05:28.927Z",
                "t": "p",
                "_updatedAt": "2023-03-13T14:33:52.957Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "bPTzNogizz7xMu84s",
                "name": "fff",
                "ts": "2023-02-08T16:30:28.212Z",
                "t": "p",
                "_updatedAt": "2023-02-08T16:32:22.973Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "82htiMFZLCtvRFqZi",
                "name": "James",
                "ts": "2023-02-06T12:34:52.974Z",
                "t": "l",
                "_updatedAt": "2023-03-30T16:41:14.880Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "EhpNtqqrMXT4QWk3z",
                "name": "telegram-channel",
                "ts": "2023-02-09T12:59:43.323Z",
                "t": "c",
                "_updatedAt": "2023-03-28T21:54:30.842Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "nSPCoYaKNbr9kzdS3",
                "name": "Test",
                "ts": "2023-04-01T18:17:51.668Z",
                "t": "l",
                "_updatedAt": "2023-04-01T22:31:27.623Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "3FxJwRrBdbLv98haWrYhzFRd2QZjNwAAXX",
                "ts": "2023-03-08T15:06:37.228Z",
                "t": "d",
                "_updatedAt": "2023-03-08T22:09:42.781Z",
                "usernames": [
                    "google-drive.bot",
                    "rodriq"
                ]
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "mLMFSg9YxHhmn7tmj",
                "name": "An agent",
                "ts": "2023-03-02T15:20:12.392Z",
                "t": "l",
                "_updatedAt": "2023-03-03T20:52:42.549Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "PPXCx99ksgSQJvdPX",
                "name": "Folorunso Yewande Susan",
                "ts": "2023-03-31T12:23:32.150Z",
                "t": "l",
                "_updatedAt": "2023-03-31T14:22:19.634Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "N9kHTGxt2mYoMmjPs",
                "name": "Test",
                "ts": "2023-04-01T22:31:55.113Z",
                "t": "l",
                "_updatedAt": "2023-04-05T15:07:25.277Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "FwC5g5re3JmcCs5TP",
                "name": "Roxie",
                "ts": "2023-04-06T18:38:43.524Z",
                "t": "l",
                "_updatedAt": "2023-04-06T18:39:46.891Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "teSNo3QPv4ebudmab",
                "name": "José Paulo Petry",
                "ts": "2023-05-22T15:21:57.348Z",
                "t": "l",
                "_updatedAt": "2023-05-22T15:25:04.855Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "2D7sdGwZNtXFhhxTN",
                "name": "Test",
                "ts": "2023-04-01T10:02:57.784Z",
                "t": "l",
                "_updatedAt": "2023-04-01T10:03:54.390Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
 
        {
            "room": {
                "_id": "w7gAEoX8ZAGaf7TDt",
                "name": "Test",
                "ts": "2023-04-01T18:17:12.480Z",
                "t": "l",
                "_updatedAt": "2023-04-01T18:17:46.149Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        },
        {
            "room": {
                "_id": "RcS8FunJvXFJJEP4j",
                "name": "omnichannel-twitter-setup",
                "ts": "2023-03-28T02:14:09.081Z",
                "t": "p",
                "_updatedAt": "2023-04-17T12:11:12.786Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        }
        {
            "room": {
                "_id": "wYmpBgzn6rj3ET8J2",
                "name": "omnichannel-whatsapp-setup",
                "ts": "2023-04-03T13:07:29.426Z",
                "t": "p",
                "_updatedAt": "2023-04-07T07:44:34.342Z"
            },
            "messages": 0,
            "lastWeekMessages": 0,
            "diffFromLastWeek": 0
        }
    ],
    "total": 90,
    "offset": 0,
    "count": 50,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have the   `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid Date**: This occurs when the `start` or `end` date does not follow the accepted format ( `2023-10-05T14:48:00.000Z`).

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Invalid Date" %}
```json
{
    "success": false,
    "error": "Match error: Failed Match.Where validation in field start"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.1.0   | Added       |
