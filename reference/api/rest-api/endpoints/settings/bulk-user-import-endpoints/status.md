# Status

Get the status of the current import operation.

{% hint style="info" %}
It requires the `run-import` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/import.status` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

### Example Call

```bash
curl --location 'http://localhost:3000/api/v1/import.status' \
--header 'x-auth-token: QizJozLOnWMi_2vWaLHhjfd-XYKT6XM40lTZ3zg1UMd' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json'
```

## Example Result

### Success

```javascript
{
  "state": "ready",
  "operation": {
    "_id": "64d51ea91558939980aab371",
    "type": "api",
    "importerKey": "api",
    "ts": "2023-08-10T17:30:17.519Z",
    "status": "importer_user_selection",
    "valid": true,
    "user": "7TY57bBj3xQXvf2i2",
    "_updatedAt": "2023-08-10T17:41:20.052Z",
    "count": {
      "total": 2,
      "users": 2
    }
  },
  "success": true
}
```

#### Operation States

| State       | Description                                                                           |
| ----------- | ------------------------------------------------------------------------------------- |
| `none`      | No import operation was ever created                                                  |
| `new`       | An operation was created but no data was added to it.                                 |
| `loading`   | A traditional importer is currently loading data from a file to the import operation. |
| `ready`     | An operation was created and has data ready to import.                                |
| `importing` | The import operation is running and the users are being created.                      |
| `error`     | An error caused the operation to stop running.                                        |
| `canceled`  | The operation was interrupted by an administrator.                                    |
| `done`      | The operation was completed successfully.                                             |

**Here are some key points to note:**

1. The operation is considered successful if it gets to process every user in the staging area, even if no user is imported.
2. You can check how many users have been imported or failed to import with the `operation.count.completed` and `operation.count.error` attributes.
3. The data from users that failed to import will remain in the staging area after the operation is complete.
4. While the operation is running, the values on `operation.count` are only updated once after every 50 users are processed.

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
