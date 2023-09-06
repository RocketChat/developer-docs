# Mailer Unsubscribe Endpoint

Send emails to users from your workspace.

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/mailer.unsubscribe` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code></td><td><code>c6Lsa9SFVFxJLR56H</code></td><td>Required</td><td>The user id of the user that created the mailer</td></tr><tr><td><code>createdAt</code></td><td><code>1692284808957</code></td><td>Required</td><td>The user id of the user that created the mailer.</td></tr></tbody></table>

### Example Payload <a href="#query-parameters" id="query-parameters"></a>

```json
{
    "_id":"c6Lsa9SFVFxJLR56H",
    "createdAt":"1692284808957"
}
```

### Example Call <a href="#query-parameters" id="query-parameters"></a>

```json
curl -L -X POST "http://localhost:3000/api/v1/mailer.unsubscribe" \
-H 'x-auth-token: mKbjO_nZwyhw5wAwxzyvbfKi-gwsczKAREXuk531nYC' \
-H 'x-user-id: BgJxHCKughQrg3TZP' \
-H 'Content-Type: application/json' \
-d '{
    "_id":"c6Lsa9SFVFxJLR56H",
    "createdAt":"1692284808957"
}'
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```javascript
{
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 5.4.0   | Added       |
