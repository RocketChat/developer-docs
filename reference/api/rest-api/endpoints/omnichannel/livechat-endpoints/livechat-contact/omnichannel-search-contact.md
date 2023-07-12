# Search Omnichannel Contact

Use this endpoint to find Omnichannel contacts by name, email, phone number, or any custom field values stored in the database.

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `api/v1/omnichannel/contact.search` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

<table><thead><tr><th width="139">Argument</th><th>Example</th><th width="154">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code></td><td><code>email@rocket.chat</code></td><td>Optional</td><td>Search contacts by Co email address</td></tr><tr><td><code>phone</code></td><td><code>+13xxxxxxxxx</code></td><td>Optional</td><td>Contact phone number</td></tr><tr><td><code>custom</code></td><td><code>fieldName=value</code></td><td>Optional</td><td>Contact custom field</td></tr></tbody></table>

## Example Call

{% hint style="info" %}
It is important to encode values having characters like **`@`**, **`+`**, **`/`** and **`*`** to avoid breaking the endpoint.
{% endhint %}



### Find contacts by Email ID&#x20;

```bash
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact.search?email=email@rocket.chat \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

### Find contacts by Phone Number&#x20;

```url
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact.search?phone=111111111 \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

### Find contacts through Custom Fields

```
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact.search?custom=field_name%3Dfield_value \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

The `custom` query parameter can be used to search for a contact by a custom field. The `custom` query parameter must be encoded by [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams).

## Example Result

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
            "hobby": "gamming"
        }
    },
    "success": true
}
```
