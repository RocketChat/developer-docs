# Status
Get the status of the current import operation.

Requires the `run-import` permission.

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/import.status` | `yes`         | `GET`       |

## Example Call

```bash
curl -H 'X-Auth-Token: YDthX6agkT6yn96u__5YmLdSCmmTZDndr4zlJmuDADC' \
     -H 'X-User-Id: 7TY57bBj3xQXvf2i2' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/import.status
```

## Example Result

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

### Operation States

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

**Notes**
1. The operation is considered successful if it gets to process every user in the staging area, even if no user is imported. 
2. You can check how many users have been imported or failed to import with the `operation.count.completed` and `operation.count.error` attributes.
3. The data from users that failed to import will remain in the staging area after the operation is complete. 
4. While the operation is running, the values on `operation.count` are only updated once after every 50 users are processed.  

## Change Log

| Version | Description                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------- |
| 6.3.0   | Added                                                                                              |
