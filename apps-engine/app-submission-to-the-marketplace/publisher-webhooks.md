# Publisher Webhooks

A marketplace publisher can register a webhook endpoint link to receive news and updates regarding their marketplace apps.

## Set Publisher Webhook Link

**Setting Webhook during publisher registration:** During your [publisher registration](./#create-a-publisher-account), you can input a link in the optional `webhook link` field.

**For already registered publishers:** This webhook information can be added or edited on their own dashboard in the **Publisher Information** section.

## Publisher Webhook Payload

The payload when an event occurs is of this format.

```json
{
  "type": "compile",
  "appName": "Out of Office Responder",
  "appID": "09a2b0d8-94d0-433d-a53e-3961a3bb0205",
  "extra": "system-compile-failure",
  "when": "2021-06-14T16:02:10.97642-03:00"
}
```

The fields are:

* **type**: The type of event. Possible events are `compile`, `adminAction` and `purchaseOrSubscription.`
* **appName**: The name of the app the event is related to.
* **appID**: The id of the app the event is related to.
* **extra**: String with extra information related to the event. Field topology is `{who did the event}-{event specific description}.`
* **when**: Timestamp for when the event happened.
