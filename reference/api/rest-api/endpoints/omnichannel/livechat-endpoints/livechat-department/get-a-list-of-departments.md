# Get a list of departments

It supports the [#pagination](../../../../#pagination "mention") parameters.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/livechat/department` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/department
```

## Example Result

```javascript
{
  "departments": [
    {
      "_id": "4swtja84kmn5WCdwL",
      "enabled": true,
      "name": "My Department",
      "description": "I have no description for this department",
      "numAgents": 1,
      "showOnRegistration": true,
      "_updatedAt": "2016-12-06T17:19:18.138Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description                 |
| ------- | --------------------------- |
| 2.2.0   | Added support to pagination |
| 0.42.0  | Added                       |

##
