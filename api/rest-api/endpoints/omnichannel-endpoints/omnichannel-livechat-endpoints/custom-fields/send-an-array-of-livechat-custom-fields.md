# Send an array of Livechat custom fields

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/custom.fields` | `no` | `POST` |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "customFields": [{
    "key": "address",
    "value": "Rocket.Chat Avenue",
    "overwrite": true
  }]
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/custom.fields \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "customFields": [{"key": "address", "value": "Rocket.Chat Avenue", "overwrite": true}]}'
```

## Example Result

```javascript
{
  "fields": [
    {
      "Key": "address",
      "value": "Rocket.Chat Avenue",
      "overwrite": true
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.70.0 | Added |

## 

