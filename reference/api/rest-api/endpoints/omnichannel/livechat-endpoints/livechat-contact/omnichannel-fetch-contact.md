---
description: Retrieves a contact information.
---

# Get Omnichannel Contact

Retrieve a contact's information.

<table><thead><tr><th width="163">HTTP Method</th><th width="296">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/omnichannel/contact</code></td><td><code>yes</code></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="196.33333333333331">Key</th><th width="226">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>contactId </code><mark style="color:red;"><code>*</code></mark></td><td><code>mAm5YZHwHMrNj8fhu</code></td><td>The contact ID.</td></tr></tbody></table>

## Example Call

{% swagger method="get" path="/api/v1/omnichannel/contact?contactId=mAm5YZHwHMrNj8fhu" baseUrl="http://localhost:3000" summary="Get the contact's information" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="contactId" required="true" %}
Contact ID
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```json
{
    "contact": {
        "_id": "653f9ce1a2f73c7460e18e82",
        "username": "guest-39",
        "ts": "2023-10-30T12:09:05.982Z",
        "token": "434lxd7iss8yh8c4m80wh",
        "_updatedAt": "2023-10-30T13:43:22.044Z",
        "contactManager": {
            "username": "kim.jane"
        },
        "livechatData": {},
        "name": "Chris",
        "phone": [
            {
                "phoneNumber": "+91123456788"
            }
        ],
        "visitorEmails": [
            {
                "address": "chris@gmail.com"
            }
        ]
    },
    "success": true
}
```
