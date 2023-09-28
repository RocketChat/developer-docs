# Confirm Enterprise License

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Confirm if the current workspace is an [enterprise edition](https://www.rocket.chat/enterprise) workspace.

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/licenses.isEnterprise` | `Optional`    | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/licenses.isEnterprise' \
--header 'x-auth-token: iqJERsuaUgzVSmPMV87RdMThc_yFhK8U5T5mr6Z5CPs' \
--header 'x-user-id: wxnehxdyBPuPyQaNa' \
```

## Example Result

### Success

```json
{
    "isEnterprise": true,
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
| 5.0.0   | Added       |
