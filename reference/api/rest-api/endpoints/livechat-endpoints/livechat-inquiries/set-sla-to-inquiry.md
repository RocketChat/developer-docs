# Set SLA to Inquiry

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Set [SLA policy ](https://docs.rocket.chat/use-rocket.chat/omnichannel/sla-policies)to an inquiry.

{% hint style="info" %}
It requires either the `view-l-room` or `manage-livechat-sla` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/inquiry.setSLA` | `YES`         | `PUT`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Payload

| Argument | Example                    | Required | Description            |
| -------- | -------------------------- | -------- | ---------------------- |
| `roomId` | `ZDYMFPpvnXgptmzMs`        | Required | The room Id            |
| `sla`    | `6417f67528384134ed600dc6` | Required | Name or Id of the SLA. |

## Example Payload

```json
{
    "roomId":"ZDYMFPpvnXgptmzMs",
    "sla":"6417f67528384134ed600dc6"
}

```

## Example Call

```bash
curl --location --request PUT 'https://writing-demo.dev.rocket.chat/api/v1/livechat/inquiry.setSLA' \
--header 'x-auth-token: fjiPBhtyFAn5JO3RDdDvKjkXToV2pd4_lb-nkdgJ_Q4' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data '{
    "roomId":"ZDYMFPpvnXgptmzMs",
    "sla":"6417f67528384134ed600dc6"
}'
```

## Example Result

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user neither has the    `view-l-room` nor `manage-livechat-sla` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid Inquiry:** This occurs when the inquiry is invalid.



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

{% tab title="Invalid Inquiry" %}
```
{
    "success": false,
    "error": "error-invalid-inquiry"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |

