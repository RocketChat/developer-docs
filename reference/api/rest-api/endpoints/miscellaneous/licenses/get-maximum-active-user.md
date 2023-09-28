# Get Maximum Active User

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieves a list of the maximum active users.

| `licenses.maxActiveUsers` | `Required` | `GET` |
| ------------------------- | ---------- | ----- |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/licenses.maxActiveUsers' \
--header 'x-auth-token: iqJERsuaUgzVSmPMV87RdMThc_yFhK8U5T5mr6Z5CPs' \
--header 'x-user-id: wxnehxdyBPuPyQaNa'
```

## Example Result

### Success

```json
{
    "maxActiveUsers": 25,
    "activeUsers": 0,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 4.0.0   | Added       |
