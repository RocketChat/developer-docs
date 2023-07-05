# Get Public Settings

Retrieve all public settings.

| Name                  | Requires Auth | Permission | Setting |
| --------------------- | ------------- | ---------- | ------- |
| `public-settings/get` | Yes           |            |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                   | Required | Description                                                                                                     |
| -------- | ------------------------- | -------- | --------------------------------------------------------------------------------------------------------------- |
| `date`   | `{ "$date": 1480377601 }` | Optional | Filters the results to  contain the updated and removed settings after the provided time. It accepts timestamp. |



## Example call to retrieve all settings

```javascript
{
    "msg": "method",
    "method": "public-settings/get",
    "id": "42"
}
```

### Response

```javascript
{
    "msg": "result",
    "id": "42",
    "result": [
        {
            "_id": "FileUpload_Enabled",
            "value": true,
            "enterprise": false,
            "requiredOnWizard": false
        },
        {
            "_id": "FileUpload_MaxFileSize",
            "value": 104857600,
            "enterprise": false,
            "requiredOnWizard": false
        },
        {
            "_id": "FileUpload_MediaTypeWhiteList",
            "value": "",
            "enterprise": false,
            "requiredOnWizard": false
        },
        {
            "_id": "FileUpload_MediaTypeBlackList",
            "value": "image/svg+xml",
            "enterprise": false,
            "requiredOnWizard": false
        },
        {
            "_id": "FileUpload_ProtectFiles",
            "value": true,
            "enterprise": false,
            "requiredOnWizard": false
        },
        {
            "_id": "FileUpload_RotateImages",
            "value": true,
            "enterprise": false,
            "requiredOnWizard": false
        },
}
```

## Example call to retrieve the updated and removed settings since the provided date

```javascript
{
    "msg": "method",
    "method": "public-settings/get",
    "id": "42",
    "params": [ { "$date": 1480377601 } ]
}
```

### Response

```javascript
"result": {
        "update": [
            {
                "_id": "FileUpload_Enabled",
                "value": true,
                "enterprise": false,
                "requiredOnWizard": false
            },
            {
                "_id": "FileUpload_MaxFileSize",
                "value": 104857600,
                "enterprise": false,
                "requiredOnWizard": false
            },
            {
                "_id": "FileUpload_MediaTypeWhiteList",
                "value": "",
                "enterprise": false,
                "requiredOnWizard": false
            },
            {
                "_id": "FileUpload_MediaTypeBlackList",
                "value": "image/svg+xml",
                "enterprise": false,
                "requiredOnWizard": false
            },
            {
                "_id": "FileUpload_ProtectFiles",
                "value": true,
                "enterprise": false,
                "requiredOnWizard": false
            },
            {
                "_id": "FileUpload_RotateImages",
                "value": true,
                "enterprise": false,
                "requiredOnWizard": false
            }
             ],
        "remove": []
    }
}
```
