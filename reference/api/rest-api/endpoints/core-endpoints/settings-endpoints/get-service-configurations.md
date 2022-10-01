# Get Service configurations

List out all the active OAuth services configured with details.

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/service.configurations` | `no`          | `GET`       |

## Example Call

```bash
curl http://localhost:3000/api/v1/service.configurations
```

## Example Result

```javascript
{
    "configurations": [
        {
            "_id": "Hq5ahzz9MWWCdeDJ8",
            "service": "google",
            "clientId": "xxxxx"
        },
        {
            "_id": "57kavS22achLH33PE",
            "service": "apple",
            "clientId": "xxxxxx"
        }
    ],
    "success": true
}
```
