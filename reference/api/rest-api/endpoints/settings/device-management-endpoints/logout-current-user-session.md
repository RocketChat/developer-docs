# Logout Current User Session

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

This endpoint allows an authenticated user to log out of any of their sessions on the workspace. It is designed specifically for the user to terminate their sessions and cannot be used to log out sessions belonging to other users on the workspace.

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/sessions/logout.me` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

| Argument    | Example             | Required | Description     |
| ----------- | ------------------- | -------- | --------------- |
| `sessionId` | `WJ2giBwm4B9mcojFi` | Required | The session id. |

## Example payload

```javascript
{
    "sessionId":"WJ2giBwm4B9mcojFi"
}
```

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/sessions/logout.me' \
--header 'Content-Type: application/json' \
--header 'X-Auth-Token: ocFlTSMfowj9tSH1vQV6ANL9SiahkKUK1KhU_PpAUtT' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--data '{
    "sessionId": "WJ2giBwm4B9mcojFi"
}'

```

## Example Result

### Success

```json
{
    "sessionId": "WJ2giBwm4B9mcojFi",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Session not found:**  Occurs when the `sessionId` doesn't belong to the current user making the request or does not exist.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Session not found" %}
```json
{
    "success": false,
    "error": "Session not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
