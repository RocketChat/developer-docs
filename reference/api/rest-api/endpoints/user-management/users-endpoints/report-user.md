# Report User

Report a user.

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/moderation.reportUser` | `yes`         | `POST`      |

### Payload <a href="#payload" id="payload"></a>

| Argument      | Example             | Required | Description                        |
| ------------- | ------------------- | -------- | ---------------------------------- |
| `userId`      | `ByehQjC44FwMeiLbX` | Required | The id of the user to be reported. |
| `description` | `test`              | Required | The reason for reporting the user. |

### Example Payload <a href="#example-call" id="example-call"></a>

```json
{
    "userId":"kdgf7sgLvwBri9rtA",
    "description":"Verbal abuse"

}
```

### Example Call <a href="#example-call" id="example-call"></a>

```json
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

### Example Result <a href="#example-result" id="example-result"></a>

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
