# Publisher Webhooks

A marketplace publisher can register a webhook endpoint link to receive news and changes regarding their marketplace apps.

## Set Publisher Webhook Link

You can go about this is two ways:

1. Setting Webhook during publisher registration. During your publisher registration you can input a link in the optional `webhook link` field

![Publisher account add webhook link](https://lh6.googleusercontent.com/EvhcOA9SiZurEjcKQMDgEED-BMD384-vN5Z1oXE5DA4uCugdZU1\_hGvAogh9d3XzFdyo8FBZWjxiZUCalCSFo1FVPtbglbsg7VG4WRVXUDmCHONW46\_si\_d5zky2\_PExe72qfZ6PM587bS9Zbg)

2\. For already registered publishers this information can be added/edited on their own dashboard in the publisher info section

![](https://lh5.googleusercontent.com/F5r8gPcsS1JWEK7sVVI2QyM9jw3LeRxWZhMBOmdNkh2vTBFDkWbEG7E0IrPz9Udgik9fNyS6p1ePnNilnu\_sxcWtWXxxh\_Xoikqn6ROZ3STltyIWrTmtbw3gEiXg1\_Tp4VgKitQ2LgI0YZXk-Q)

## Publisher Webhook Payload

The payload when an event occurs is of this format&#x20;

```json
{
  "type": "compile",
  "appName": "Out of Office Responder",
  "appID": "09a2b0d8-94d0-433d-a53e-3961a3bb0205",
  "extra": "system-compile-failure",
  "when": "2021-06-14T16:02:10.97642-03:00"
}
```

The fields are:&#x20;

* **type**: The type of event. Possible events are `compile`, `adminAction` and `purchaseOrSubscription`
* **appName**: The name of the app the event is related to&#x20;
* **appID**: The id of the app the event is related to&#x20;
* **extra**: String with extra information related to the event. Field topology is `{who did the event}-{event specific description}`
* **when**: Timestamp for when the event happened
