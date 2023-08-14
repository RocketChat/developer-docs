# Run

Process the data from the current import operation, creating the users on Rocket.Chat. It requires the current import operation state to be `ready` and it changes the operation state to `importing.`

{% hint style="success" %}
It will return success if the conditions to start the process are met, without waiting for the import to finish.
{% endhint %}

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `/api/v1/import.run` | `yes`         | `POST`      |

{% hint style="warning" %}
* If a user can not be imported successfully it'll be flagged but the operation will not stop.
* If a user's email or username is already in use, it'll not be created.
* Only the users that were imported successfully will be removed from the staging area.
{% endhint %}

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

### Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/import.run' \
--header 'x-auth-token: QizJozLOnWMi_2vWaLHhjfd-XYKT6XM40lTZ3zg1UMd' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \

```

## Example Result

### Success

```javascript
{
  "success": true
}
```

### Error

* **No Permission**: This occurs when the authenticated user doesn't have the  `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
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
| `6.3.0` | Added       |
