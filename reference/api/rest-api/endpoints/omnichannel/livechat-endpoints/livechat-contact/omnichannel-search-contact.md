# Search Omnichannel Contacts

Find Omnichannel contacts by name, email, phone number, or any custom field values stored in the database.

<table><thead><tr><th width="163">HTTP Method</th><th width="296">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/omnichannel/contact.search</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

The following query parameters are optional:

<table><thead><tr><th width="139">Key</th><th width="229">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code></td><td><code>email@rocket.chat</code></td><td>The contact's email address.</td></tr><tr><td><code>phone</code></td><td><code>+1367895436</code></td><td>The contact's phone number.</td></tr><tr><td><code>custom</code></td><td><code>fieldName=value</code></td><td>The defined custom fields.</td></tr></tbody></table>

## Example Call

{% hint style="info" %}
Encode values having characters like **`@`**,**`+`**, **`/`**and **`*`** to avoid breaking the endpoint.
{% endhint %}

The request to search contacts with the email and phone number is as follows:

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/omnichannel/contact.search?email=mende%40mail.com&phone=447587922' \
--header 'X-Auth-Token: b5BKhblglC5OU0AfB_Tl9dKmOb0zXUvWK-nhNT_aE8V' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

To find contacts using custom fields, use the `custom` query parameter. The `custom` query parameter must be encoded by [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams). For example, to search contacts with premium subscription, the request is as follows:

{% code overflow="wrap" %}
```powershell
curl --location --globoff 'http://localhost:3000/api/v1/omnichannel/contact.search?custom={%20%22Subscription%22%3A%20%22premium%22%20}' \
--header 'X-Auth-Token: b5BKhblglC5OU0AfB_Tl9dKmOb0zXUvWK-nhNT_aE8V' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "contact": {
        "_id": "62fbed6d337291dc9a68ff89",
        "username": "guest-16",
        "status": "online",
        "ts": "2022-08-16T19:18:05.380Z",
        "_updatedAt": "2022-08-23T17:58:37.254Z",
        "department": "MgzoccgEFHZ856i97",
        "name": "Kev",
        "token": "969X86icKLRduGAKK",
        "visitorEmails": [
            {
                "address": "email@rocket.chat"
            }
        ],
        "lastChat": {
            "_id": "CT5bru2WjJ2EsmGbH",
            "ts": "2022-08-16T19:24:35.916Z"
        },
        "livechatData": {
            "hobby": "gaming"
        }
    },
    "success": true
}
```
