---
description: Retrieve the conversation transfer history from one department to another.
---

# Get Department Transfer History

Retrieve the department transfer history for a room.

<table><thead><tr><th width="163">HTTP Method</th><th width="346">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/transfer.history/:rid</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-rooms`
{% endhint %}

## Path Variables

<table><thead><tr><th width="212.33333333333331">Key</th><th width="252">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>zRAeTszXor8CCPceB</code></td><td>The room ID.</td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention")query parameters.

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/transfer.history/:rid\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "history": [],
    "count": 0,
    "offset": 0,{
    "history": [
        {
            "transferredBy": {
                "_id": "646b3be5671066d5f560818d",
                "username": "guest-20",
                "name": "Patou",
                "type": "visitor"
            },
            "ts": "2023-11-08T13:12:42.423Z",
            "scope": "department",
            "previousDepartment": "64181a0728384134ed600dcc",
            "nextDepartment": {
                "_id": "649230d479f5c6e276cf4a12",
                "name": "TestBH"
            }
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
    "total": 0,
    "success": true
}
```
