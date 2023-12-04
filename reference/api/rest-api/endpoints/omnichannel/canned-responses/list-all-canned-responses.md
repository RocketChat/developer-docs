# List All Canned Responses

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get a list of all [canned responses](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses) in the workspace. It is helpful for [omnichannel managers](https://docs.rocket.chat/use-rocket.chat/omnichannel/managers) to get all canned responses in the workspace, including private and departmental canned responses.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/canned-responses</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-canned-responses`
* `view-all-canned-responses`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters and the [#query-and-fields](../../../#query-and-fields "mention") parameters. Additional optional parameters are as follows:

<table><thead><tr><th width="175">Key</th><th width="211">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>shortcut</code><mark style="color:red;"><code>*</code></mark></td><td><code>card-declined</code></td><td>The shortcut to trigger the message snippet.</td></tr><tr><td><code>text</code><mark style="color:red;"><code>*</code></mark></td><td><code>reasons for your card malfunction</code></td><td>The message snippet.</td></tr><tr><td><code>scope</code><mark style="color:red;"><code>*</code></mark></td><td><code>global</code></td><td>The scope of the canned response. It can either be <code>global</code>, <code>user</code> or <code>department</code>.</td></tr><tr><td><code>tags</code></td><td><code>card</code></td><td>The tags for your canned response.</td></tr><tr><td><code>departmentId</code></td><td><code>64181a0728384134ed600dcc</code></td><td>The <code>departmentId</code> where the canned response belongs to. It is required if the <code>scope</code> is <code>department</code>.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/canned-responses' \
--header 'x-auth-token: Ja29cTtF-wkmIBCBysrknSoYf' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Response

### Success

```json
{
    "cannedResponses": [
        {
            "_id": "646c747ca8c3a3ba32d0e2e8",
            "shortcut": "Denied",
            "text": "This is an example",
            "scope": "global",
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "kim.jane"
            },
            "_createdAt": "2023-05-23T08:08:28.241Z",
            "_updatedAt": "2023-05-23T08:08:28.241Z"
        },
        {
            "_id": "646c6ed9a8c3a3ba32d0e2db",
            "shortcut": "my-new-canned",
            "text": "This is an example",
            "scope": "global",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "doe.john"
            },
            "_createdAt": "2023-05-23T07:44:25.912Z",
            "_updatedAt": "2023-05-23T07:44:25.912Z"
        },
        {
            "_id": "646c7350a8c3a3ba32d0e2e0",
            "shortcut": "my-new-canned-",
            "text": "This is an example",
            "scope": "hi",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "jane.mary"
            },
            "_createdAt": "2023-05-23T08:03:28.148Z",
            "_updatedAt": "2023-05-23T08:03:28.148Z"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-canned-responses` and `view-all-canned-responses` permission.

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
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
