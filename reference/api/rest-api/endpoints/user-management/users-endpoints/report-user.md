# Report User

<table><thead><tr><th width="166">HTTP Method</th><th width="342">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/moderation.reportUser</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters <a href="#payload" id="payload"></a>

<table><thead><tr><th width="199.33333333333331">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The ID of the user to be reported.</td></tr><tr><td><code>description</code><mark style="color:red;"><code>*</code></mark></td><td><code>test</code></td><td>The reason for reporting the user.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

```powershell
curl --location "http://localhost:3000/api/v1/moderation.reportUser" \
--header 'x-auth-token: _209_8t5fK_W1tEMyFwWZCXR44QOWjgdSJ8Hg6oX3ns' \
--header 'x-user-id: rmbMnnpqkuxEbrajt' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--data '{
    "userId":"BgJxHCKughQrg3TZP",
    "description":"Verbal abuse"

}'
```

## Example Response <a href="#example-result" id="example-result"></a>

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid UserId**: Occurs when the userId is invalid or does not belong to any user in the workspace.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Invalid UserId" %}
```json
{
    "success": false,
    "error": "Invalid user id provided."
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
