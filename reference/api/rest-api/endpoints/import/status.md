# Status
Get the status of the current import operation.

Requires the `run-import` permission.

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/import.status` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/import.status
```

## Example Result

```javascript
{
   "success": true,
   "state": "ready",
   "operation": {
        "type": "api",
        "importerKey": "api",
        "ts": "2016-09-13T14:57:56.037Z",
        "status": "importer_user_selection",
        "valid": true,
        "user" "aobEdbYhXfu5hkeqG",
        "_updatedAt": "2016-09-13T14:57:56.037Z",
        "count": {
            "total": 8000,
            "users": 8000,
            "messages": 0,
            "channels": 0,
            "completed": 0,
            "error": 0
        }
    }
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
