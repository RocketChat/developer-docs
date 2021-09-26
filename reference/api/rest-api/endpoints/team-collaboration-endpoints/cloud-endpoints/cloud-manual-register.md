---
description: Manually register a workspace
---

# Cloud Manual Register

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/cloud.manualRegister` | `YES` | `POST` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/cloud.manualRegister\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
 -d "cloudBlob="""
```

## Result

```javascript
{
    "success": false,
    "error": "Workspace is already registered"
}
```

